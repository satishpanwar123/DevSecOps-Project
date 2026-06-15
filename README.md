<div align="center">
  <img src="https://github.com/krishnaacharyaa/wanderlust/assets/116620586/17ba9da6-225f-481d-87c0-5d5a010a9538" alt="Wanderlust Header" width="100%" style="border-radius: 8px; box-shadow: 0 4px 12px rgba(0,0,0,0.15);">
  <br><br>
  <h1>Wanderlust 🌍✈️</h1>
  <h3>The Ultimate Travel Blog &amp; DevSecOps Showcase</h3>
</div>

<hr>

<!-- Pipeline Architecture Overview -->
<div style="padding: 10px; margin-bottom: 25px;">
  <h2 align="center" style="color: #0052cc;">🗺️ Pipeline Architecture Overview</h2>
  <p align="center" style="font-size: 1.1em; color: #666;">End-to-end view of the CI, Security, and Deployment stages</p>

  <div align="center">
    <img src="pipeline-architecture.png" alt="DevSecOps Pipeline Architecture Diagram" width="100%" style="border-radius: 8px; border: 1.5px solid #e0e0e0; box-shadow: 0 4px 16px rgba(0,0,0,0.12);">
  </div>
</div>

<hr>

<!-- Pipeline Section -->
<div style="padding: 10px; margin-bottom: 25px;">
  <h2 align="center" style="color: #0052cc;">🛠️ DevSecOps Pipeline</h2>
  <p align="center" style="font-size: 1.1em; color: #666;">Automated CI/CD, Code Quality, Security Scanning, and Containerized Deployment</p>

  <div align="center">
    <img src="pipeline.png" alt="DevSecOps Pipeline" width="100%" style="border-radius: 8px; border: 1.5px dashed #cccccc; box-shadow: 0 4px 12px rgba(0,0,0,0.1);">
  </div>

  <h3 style="color: #333; margin-top: 20px;">Pipeline Stages</h3>
  <table width="100%" style="border-collapse: collapse; margin-top: 15px; font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif;">
    <thead>
      <tr bgcolor="#f2f2f2">
        <th style="padding: 10px; border: 1px solid #ddd; text-align: left;">Stage</th>
        <th style="padding: 10px; border: 1px solid #ddd; text-align: left;">Description</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td style="padding: 10px; border: 1px solid #ddd;"><strong>1. Clone Code From GitHub</strong></td>
        <td style="padding: 10px; border: 1px solid #ddd;">Clones the latest code from the <code>main</code> branch of the repository.</td>
      </tr>
      <tr>
        <td style="padding: 10px; border: 1px solid #ddd;"><strong>2. SonarQube Quality Analysis</strong></td>
        <td style="padding: 10px; border: 1px solid #ddd;">Runs static code analysis (SAST) using SonarQube scanner to detect bugs, vulnerabilities, and code smells.</td>
      </tr>
      <tr>
        <td style="padding: 10px; border: 1px solid #ddd;"><strong>3. OWASP Dependency Check</strong></td>
        <td style="padding: 10px; border: 1px solid #ddd;">Scans project dependencies using the OWASP Dependency-Check tool with NVD API Key validation to identify known CVEs.</td>
      </tr>
      <tr>
        <td style="padding: 10px; border: 1px solid #ddd;"><strong>4. Sonar Quality Gate Scan</strong></td>
        <td style="padding: 10px; border: 1px solid #ddd;">Waits for the SonarQube analysis quality gate results (non-blocking: <code>abortPipeline: false</code>).</td>
      </tr>
      <tr>
        <td style="padding: 10px; border: 1px solid #ddd;"><strong>5. Trivy File System Scan</strong></td>
        <td style="padding: 10px; border: 1px solid #ddd;">Scans the filesystem for security misconfigurations, vulnerabilities, and hardcoded secrets using Trivy.</td>
      </tr>
      <tr>
        <td style="padding: 10px; border: 1px solid #ddd;"><strong>6. Deploy using Docker Compose</strong></td>
        <td style="padding: 10px; border: 1px solid #ddd;">Generates the runtime configuration (<code>.env.docker</code>) and deploys/builds the application services (Node backend + React frontend + MongoDB + Redis) using Docker Compose.</td>
      </tr>
    </tbody>
  </table>

  <h3 style="color: #333; margin-top: 25px;">Jenkinsfile (Declarative Pipeline)</h3>
  <p>To run this pipeline in Jenkins, create a new pipeline job and use the following script:</p>

```groovy
pipeline {
    agent any
    environment {
        SONAR_HOME = tool "Sonar"
    }
    stages {
        stage("Clone Code From GitHub") {
            steps {
                git url: "https://github.com/satishpanwar123/DevSecOps-Project.git", branch: "main"
            }
        }
        stage("SonarQube Quality Analysis") {
            steps {
                withSonarQubeEnv("Sonar") {
                    sh "$SONAR_HOME/bin/sonar-scanner -Dsonar.projectName=DevSecOps-Project -Dsonar.projectKey=DevSecOps-Project"
                }
            }
        }
        stage("OWASP Dependency Check") {
            steps { 
                // Using withCredentials safely binds the secret text to an environment variable
                withCredentials([string(credentialsId: 'nvd-api-key-id', variable: 'NVD_SECRET_KEY')]) {
                    // FIX: Removed '--purge' and securely referenced the key via env.NVD_SECRET_KEY
                    dependencyCheck additionalArguments: "--scan ./ --nvdApiKey ${env.NVD_SECRET_KEY}", odcInstallation: 'dc'
                }
                dependencyCheckPublisher pattern: '**/dependency-check-report.xml'
            }
        }
        stage("Sonar Quality Gate scan") {
            steps {
                timeout(time: 2, unit: "MINUTES") {
                    waitForQualityGate abortPipeline: false
                }
            }
        }
        stage("Trivy File System Scan") {
            steps {
                sh "trivy fs --format table -o trivy-fs-report.html ."
            }
        }
        stage('Deploy using Docker compose') {
            steps {
                sh '''
                # FIX: Switched PORT to 8080 to satisfy the container Dockerfile HEALTHCHECK block
                echo "PORT=8080" > backend/.env.docker
                echo "MONGODB_URI=mongodb://mongodb:27017/wanderlust" >> backend/.env.docker
                echo "JWT_SECRET=your_super_secret_jwt_key" >> backend/.env.docker
                
                docker-compose up -d --build --force-recreate
                '''
            }
        }
    }
}
```
</div>

<hr>

<!-- Features -->
<div style="padding: 10px; margin-bottom: 20px;">
  <h2><img src="https://github.com/Meetjain1/wanderlust/assets/133582566/1ee5934a-27be-4502-a7bf-e6a8c78fe5a3" width="30" height="30" style="vertical-align: middle;"> Features</h2>
  <ul>
    <li><strong>Featured Posts</strong>: Highlight top travel stories and destinations on the homepage to showcase the best content and inspire readers with exciting travel experiences.</li>
    <li><strong>User-Friendly Interface</strong>: Navigate effortlessly through captivating travel content with our intuitive design.</li>
    <li><strong>Discover By Topic Categories</strong>: Explore diverse travel experiences categorized by Travel, Nature, City, Adventure, and Beaches.</li>
  </ul>
</div>

<hr>

<!-- Contributors -->
<div style="padding: 10px; margin-bottom: 20px;" align="center">
  <h2><img src="https://github.com/Meetjain1/wanderlust/assets/133582566/20610b38-b287-4bf0-8f28-932b9c76163d" width="35" height="35" style="vertical-align: middle;"> Contributors</h2>
  <p>We extend our heartfelt gratitude for your invaluable contribution to our project! Your efforts play a pivotal role in elevating Wanderlust to greater heights. 😊</p>
  <div>
    <a href="https://github.com/satishpanwar123/DevSecOps-Project/graphs/contributors">
      <img width="90%" src="https://contrib.rocks/image?repo=satishpanwar123/DevSecOps-Project" style="max-width: 800px; border-radius: 8px;" />
    </a>
  </div>
</div>

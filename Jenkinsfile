@Library("Shared") _
pipeline {
    agent any
    environment {
        SONAR_HOME = tool "Sonar"
    }
    stages {
        stage("Clone Code From GitHub") {
            steps {
                git url: "https://github.com/Sujalv787/DevSecOps-Project.git", branch: "main"
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

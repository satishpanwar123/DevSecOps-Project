<div align="center">
  <img src="https://github.com/krishnaacharyaa/wanderlust/assets/116620586/17ba9da6-225f-481d-87c0-5d5a010a9538" alt="Wanderlust Header" width="100%" style="border-radius: 8px; box-shadow: 0 4px 12px rgba(0,0,0,0.15);">
  <br><br>
  <h1>Wanderlust 🌍✈️</h1>
  <h3>The Ultimate Travel Blog & DevSecOps Showcase</h3>
</div>

<hr>

<div style="padding: 10px; background-color: #f8f9fa; border-left: 5px solid #0052cc; border-radius: 4px; margin-bottom: 20px;">
  <h2 style="margin-top: 0; color: #333;">🔗 Important Links</h2>
  <table border="0" cellpadding="10" cellspacing="0" width="100%" style="background-color: #ffffff; border-radius: 8px; border: 1px solid #e0e0e0; border-collapse: collapse;">
    <tr style="border-bottom: 1px solid #eeeeee;">
        <td width="60" align="center"><img src="https://cdn-icons-png.flaticon.com/512/5968/5968756.png" alt="Discord Logo" width="40"></td>
        <td><a href="https://discord.gg/FEKasAdCrG" style="text-decoration: none; color: #5865F2; font-weight: bold;">Join our project's Discord Channel here</a></td>
    </tr>
    <tr style="border-bottom: 1px solid #eeeeee;">
        <td width="60" align="center"><img src="https://cdn-icons-png.flaticon.com/512/5968/5968705.png" alt="Figma Logo" width="40"></td>
        <td><a href="https://www.figma.com/file/zqNcWGGKBo5Q2TwwVgR6G5/WanderLust--A-Travel-Blog-App?type=design&node-id=0%3A1&mode=design&t=c4oCG8N1Fjf7pxTt-1" style="text-decoration: none; color: #F24E1E; font-weight: bold;">Find our project's Figma links here</a></td>
    </tr>
    <tr>
        <td width="60" align="center"><img src="https://cdn-icons-png.flaticon.com/512/1384/1384060.png" alt="YouTube Logo" width="40"></td>
        <td><a href="https://youtu.be/ANfC1u_N_A0?feature=shared" style="text-decoration: none; color: #FF0000; font-weight: bold;">Find our Collaboration Video with TrainwithShubham here</a></td>
    </tr>
  </table>
</div>

<hr>

<!-- Pipeline Section -->
<div style="padding: 10px; margin-bottom: 25px;">
  <h2 align="center" style="color: #0052cc;">🛠️ DevSecOps Pipeline Architecture</h2>
  <p align="center" style="font-size: 1.1em; color: #666;">Automated CI/CD, Code Quality, Security Scanning, and Containerized Deployment</p>

  <table width="100%" style="border-collapse: collapse; border: 1.5px dashed #cccccc; font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Helvetica, Arial, sans-serif; border-radius: 8px;">
    <!-- CI Row -->
    <tr style="border-bottom: 1.5px dashed #cccccc;">
      <td width="6%" bgcolor="#0052cc" align="center" style="color: white; font-weight: bold; font-size: 1.1em; padding: 20px; text-transform: uppercase; letter-spacing: 1px;">
        CI
      </td>
      <td width="94%" bgcolor="#ffffff" style="padding: 20px 10px;">
        <table border="0" cellpadding="0" cellspacing="0" width="100%" align="center">
          <tr>
            <!-- Github -->
            <td align="center" valign="top" width="20%">
              <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/github/github-original.svg" width="45" height="45"><br>
              <strong style="font-size: 0.95em;">GitHub</strong><br>
              <font size="1.5" color="#666666">DevSecOps-Project<br>branch: main</font>
            </td>
            <!-- Arrow -->
            <td align="center" valign="middle" width="6%">
              <font size="1.5" color="#0052cc">🔵<br>git clone<br>➔</font>
            </td>
            <!-- Jenkins -->
            <td align="center" valign="top" width="20%">
              <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/jenkins/jenkins-original.svg" width="45" height="45"><br>
              <strong style="font-size: 0.95em;">Jenkins</strong><br>
              <font size="1.5" color="#666666">agent any<br>SONAR_HOME tool</font>
            </td>
            <!-- Arrow -->
            <td align="center" valign="middle" width="6%">
              <font size="1.5" color="#0052cc">🔵<br>run scanner<br>➔</font>
            </td>
            <!-- SonarQube -->
            <td align="center" valign="top" width="20%">
              <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/sonarqube/sonarqube-original.svg" width="45" height="45"><br>
              <strong style="font-size: 0.95em;">SonarQube</strong><br>
              <font size="1.5" color="#666666">SAST - quality<br>security hotspots</font>
            </td>
            <!-- Arrow -->
            <td align="center" valign="middle" width="8%">
              <font size="1.5" color="#0052cc">🔵<br>webhook - 2 min<br>➔</font>
            </td>
            <!-- Quality Gate -->
            <td align="center" valign="top" width="20%">
              <img src="https://cdn-icons-png.flaticon.com/512/3256/3256783.png" width="45" height="45"><br>
              <strong style="font-size: 0.95em;">Quality Gate</strong><br>
              <font size="1.5" color="#666666">waitForQualityGate<br>abortPipeline: false</font>
            </td>
          </tr>
        </table>
      </td>
    </tr>

    <!-- SECURITY Row -->
    <tr style="border-bottom: 1.5px dashed #cccccc;">
      <td bgcolor="#d9381e" align="center" style="color: white; font-weight: bold; font-size: 1.1em; padding: 20px; text-transform: uppercase; letter-spacing: 1px;">
        SECURITY
      </td>
      <td bgcolor="#ffffff" style="padding: 20px 10px;">
        <table border="0" cellpadding="0" cellspacing="0" width="100%" align="center">
          <tr>
            <!-- OWASP -->
            <td align="center" valign="top" width="28%">
              <img src="https://cdn-icons-png.flaticon.com/512/1000/1000959.png" width="45" height="45"><br>
              <strong style="font-size: 0.95em;">OWASP</strong><br>
              <font size="1.5" color="#666666">Dependency Check<br>NVD API - CVE scan</font>
            </td>
            <!-- Arrow -->
            <td align="center" valign="middle" width="8%">
              <font size="1.5" color="#d9381e">🔴<br>dep-check-report.xml<br>➔</font>
            </td>
            <!-- Trivy -->
            <td align="center" valign="top" width="28%">
              <img src="https://cdn-icons-png.flaticon.com/512/3135/3135715.png" width="45" height="45"><br>
              <strong style="font-size: 0.95em;">Trivy</strong><br>
              <font size="1.5" color="#666666">fs scan - secrets<br>misconfigs</font>
            </td>
            <!-- Arrow -->
            <td align="center" valign="middle" width="8%">
              <font size="1.5" color="#d9381e">🔴<br>trivy-fs-report.html<br>➔</font>
            </td>
            <!-- Security Reports -->
            <td align="center" valign="top" width="28%">
              <img src="https://cdn-icons-png.flaticon.com/512/2921/2921222.png" width="45" height="45"><br>
              <strong style="font-size: 0.95em;">Security Reports</strong><br>
              <font size="1.5" color="#666666">XML - HTML<br>published to Jenkins</font>
            </td>
          </tr>
        </table>
      </td>
    </tr>

    <!-- DEPLOY Row -->
    <tr>
      <td bgcolor="#00875a" align="center" style="color: white; font-weight: bold; font-size: 1.1em; padding: 20px; text-transform: uppercase; letter-spacing: 1px;">
        DEPLOY
      </td>
      <td bgcolor="#ffffff" style="padding: 20px 10px;">
        <table border="0" cellpadding="0" cellspacing="0" width="100%" align="center">
          <tr>
            <!-- env.docker -->
            <td align="center" valign="top" width="28%">
              <img src="https://cdn-icons-png.flaticon.com/512/825/825590.png" width="45" height="45"><br>
              <strong style="font-size: 0.95em;">.env.docker</strong><br>
              <font size="1.5" color="#666666">PORT=8081<br>MONGODB_URI · JWT</font>
            </td>
            <!-- Arrow -->
            <td align="center" valign="middle" width="8%">
              <font size="1.5" color="#00875a">🟢<br>inject config<br>➔</font>
            </td>
            <!-- Docker Compose -->
            <td align="center" valign="top" width="28%">
              <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/docker/docker-original.svg" width="45" height="45"><br>
              <strong style="font-size: 0.95em;">Docker Compose</strong><br>
              <font size="1.5" color="#666666">--build<br>--force-recreate</font>
            </td>
            <!-- Arrow -->
            <td align="center" valign="middle" width="8%">
              <font size="1.5" color="#00875a">🟢<br>up -d :8081<br>➔</font>
            </td>
            <!-- Wanderlust -->
            <td align="center" valign="top" width="28%">
              <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/mongodb/mongodb-original.svg" width="45" height="45"><br>
              <strong style="font-size: 0.95em;">Wanderlust</strong><br>
              <font size="1.5" color="#666666">App - MongoDB<br>:27017</font>
            </td>
          </tr>
        </table>
      </td>
    </tr>
  </table>

  <p align="center" style="margin-top: 15px; font-size: 0.9em;">
    <span style="color: #0052cc;">🔵 <strong>CI Flow</strong></span> &nbsp;&nbsp;|&nbsp;&nbsp;
    <span style="color: #d9381e;">🔴 <strong>Security Scan</strong></span> &nbsp;&nbsp;|&nbsp;&nbsp;
    <span style="color: #00875a;">🟢 <strong>Deployment</strong></span> &nbsp;&nbsp;|&nbsp;&nbsp;
    <span style="color: #666;">--- <strong>Stage boundary</strong></span>
  </p>
</div>

<hr>

<!-- Goal -->
<div style="padding: 10px; margin-bottom: 20px;">
  <h2><img src="https://github.com/Meetjain1/wanderlust/assets/133582566/4a07b161-b8d6-4803-804a-3b0db699023e" width="30" height="30" style="vertical-align: middle;"> Goal of this project</h2>
  <p>At its core, this project embodies two important aims:</p>
  <ol>
    <li><strong>Start Your Open Source Journey</strong>: It's aimed to kickstart your open-source journey. Here, you'll learn the basics of Git and get a solid grip on the MERN stack. We strongly believe that learning and building should go hand in hand.</li>
    <li><strong>React Mastery</strong>: Once you've got the basics down, a whole new adventure begins of mastering React. This project covers everything, from simple form validation to advanced performance enhancements. Much more cool features are planned for the near future as the contributor community grows.</li>
  </ol>
  <p><em>We want you to get the most out of this project—it's all about learning, contributing, and growing in the open-source community.</em></p>
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

<!-- Contribution -->
<div style="padding: 10px; margin-bottom: 20px;">
  <h2><img src="https://github.com/Meetjain1/wanderlust/assets/133582566/90f3930e-5a12-4a4e-8ac9-0dc7d5396adb" width="30" height="30" style="vertical-align: middle;"> Ready to Contribute?</h2>
  <p>Kindly go through <a href="https://github.com/satishpanwar123/DevSecOps-Project/blob/main/.github/CONTRIBUTING.md">CONTRIBUTING.md</a> to understand everything from setup to contributing guidelines.</p>
</div>

<hr>

<!-- Open Source Programs -->
<div style="padding: 10px; margin-bottom: 20px;">
  <h2><img src="https://github.com/Tarikul-Islam-Anik/Animated-Fluent-Emojis/blob/master/Emojis/Hand%20gestures/Flexed%20Biceps.png?raw=true" width="30" height="30" style="vertical-align: middle;"> Open Source Programs</h2>
  <table border="1" cellpadding="10" style="border-collapse: collapse; border: 1px solid #dddddd; background-color: #fafafa; border-radius: 6px; width: 100%;">
    <tr>
      <td rowspan="2" width="120" align="center">
        <img src="https://github.com/Meetjain1/wanderlust/assets/133582566/21b2bc42-bdd5-487a-a083-1b262c2f6d9b" alt="GSSOC Logo" width="100" height="55" style="object-fit: contain;">
      </td>
      <td>
        <strong>GSSOC 2024</strong>
      </td>
    </tr>
    <tr>
      <td>
        This project is part of GirlScript Summer of Code. We warmly welcome contributions from the community to help elevate Wanderlust.
      </td>
    </tr>
  </table>
</div>

<hr>

<!-- Code of Conduct -->
<div style="padding: 10px; margin-bottom: 20px;">
  <h2><img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Animated-Fluent-Emojis/master/Emojis/Hand%20gestures/Handshake.png" width="30" height="30" style="vertical-align: middle;"> Code of Conduct</h2>
  <p>Please note that this project is released with a <a href="./.github/CODE_OF_CONDUCT.md">Contributor Code of Conduct</a>. By participating in this project you agree to abide by its terms.</p>
</div>

<hr>

<!-- License -->
<div style="padding: 10px; margin-bottom: 20px;">
  <h2><img src="https://raw.githubusercontent.com/Tarikul-Islam-Anik/Animated-Fluent-Emojis/master/Emojis/Objects/Page%20with%20Curl.png" width="30" height="30" style="vertical-align: middle;"> License</h2>
  <p>This project is licensed under the <a href="./LICENSE">MIT License</a>.</p>
</div>

<hr>

<!-- Support -->
<div style="padding: 10px; margin-bottom: 20px;">
  <h2><img src="https://github.com/Meetjain1/wanderlust/assets/133582566/af38ec84-7387-4af7-af85-8f408a4654e9" width="30" height="30" style="vertical-align: middle;"> Show Your Support</h2>
  <p>If you find this project interesting and inspiring, please consider showing your support by starring it on GitHub! Your star goes a long way in helping us reach more developers and encourages us to keep enhancing the project.</p>
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

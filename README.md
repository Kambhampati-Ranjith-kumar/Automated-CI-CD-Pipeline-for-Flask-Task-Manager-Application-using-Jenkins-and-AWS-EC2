# 🚀 Automated CI/CD Pipeline For Flask Task Manager

This project demonstrates a complete  CI/CD pipeline using Jenkins, GitHub Webhook, and AWS EC2 to automatically build, test, and deploy a Flask application.

WHenever new code is pushed to GitHub, Jenkins automatically triggers the pipeline to deploy the application.

# 📌 Project Overview

The goal of this project is to implement Continious Integration and Continuous Development(CI/CD) using Jenkins.

### Pipeline Overview:

1.Developer pushes code to GitHub
2.GitHub Webhook triggers Jenkins build
3.Jenkins installs dependencies
4.Jenkins runs automated tests.
5.Jenkins deploys application to AWS EC2.
6.Flask application runs automatically

## 🧰 Technologu Used

| Technology | Purpose |
|---------|-------------|
| Jenkins | CI/CD automation |
| GitHub | Source code repository |
| AWS EC2 | Application hosting |
| Python | Backend language |
| Flask  | Web framework |
| Pytest  | Unit testing |
| Linux   | Server environment |
| SSH  | Secure deployment |

## 🏗️ Architecture Diagram
```
Developer
   |
   | git push
   v
Github Repository
   |
   | Webhook Trigger
   v
Jenkins Pipeline
   |
   |-- Install Dependencies
   |-- Run Tests (Pytest)
   |-- Deploy Application
   v
AWS EC2 Server
   |
   v
Flask Application
   |
   v
http://EC2-IP:5000
```

## 📂 Project Structure
```
Automated-CI-CD-Pipeline
|
|-- app.py
|-- requirements.txt
|-- Jenkinsfile
|-- test_app.py
|
|__templates
    |__ index.html
```

## ⚙️ Jenkins Pipeline Stages

1️⃣ Install Dependencies
```
pip3 install --break-system-packages -r requirements.txt
```
2️⃣ Run Tests
```
python3 -m pytest
```
3️⃣ Depl0y Applications
```
scp project files --> EC2 server ssh into EC2 --> restart Flask server
```

## 🔁 CI/CD Workflow
```
Code Commit
    |
    v
GitHub Repository
    |
    v
Webhook Trigger
    |
    v
Jenkins Pipeline
    |
    |--Insatll Dependencies
    |--Run Tests
    |--Deploy Applications
            |
            v
      AWS EC2 Server
            |
            v
      Flask Web App
```
## 🌐 Applications Preview

### Access the deployed application:
```
http://<EC2-public-IP>:5000
```
## 🧪 Automated Testing

Unit tests are written using Pytest

Jenkins executes these tests automaticallyt during every pipeline run.

## 🔐 Jenkins Credentials

Secure SSH authentication is used to deploy the application to AWS EC2.
```
sshagent(['AWS-login'])
```
This ensures safe remote access from Jenkins to the server.

## 🚀 Run the Application

CLone the repository
```
git clone < repo-url>
```
Install Dependencies
```
pip3 install -r requirements.txt
```
Run the Flask application
```
python3 app.py
```
Open browser
```
http://localhost:5000
```

## 👨‍💻 Author
##### Ranjith Kumar


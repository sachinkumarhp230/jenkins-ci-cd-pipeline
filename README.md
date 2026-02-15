# 🚀 Jenkins CI/CD Pipeline – Static Website Deployment

## 📌 Project Overview

This project demonstrates a basic CI/CD pipeline using Jenkins to deploy a static website to a remote Ubuntu server.

The pipeline automates:

- Code checkout from GitHub
- Basic validation testing
- Deployment to remote server via SCP
- Success and failure notifications

The CI/CD logic is defined in the `Jenkinsfile` located in the repository root.

---

## 🏗️ Architecture

GitHub Repository  
        ↓  
Jenkins Server  
        ↓  
Remote Ubuntu Server (Nginx)  
        ↓  
Static Website Hosted

---

## 🔄 Pipeline Stages

The pipeline contains the following stages:

1. **Checkout** – Pull source code from GitHub.
2. **Build** – No build required (static website).
3. **Test** – Validate presence of `index.html`.
4. **Deploy** – Transfer file to remote server using SCP.

---

## 📂 Repository Structure

jenkins-ci-cd-pipeline/
│
├── Jenkinsfile
├── index.html
└── README.md


---

## ⚙️ Prerequisites

- Jenkins installed
- Git installed on Jenkins server
- SSH key configured between Jenkins and target server
- Ubuntu server with Nginx installed
- Port 22 and 80 open in security group

---

## 🔑 Setup Steps

### 1. Configure Jenkins Pipeline

- Create a new Pipeline job
- Select "Pipeline script from SCM"
- Provide GitHub repository URL
- Branch: main

### 2. Configure SSH Access

Generate SSH key on Jenkins server:

ssh-keygen


Copy public key to remote server:

ssh-copy-id ubuntu@<SERVER-IP>


---

## 🌐 Access Application

After successful deployment:

http://<SERVER-IP>


---

## 🎯 DevOps Concepts Demonstrated

- Continuous Integration
- Continuous Deployment
- Jenkins Declarative Pipelines
- GitHub Integration
- Remote Server Automation
- Basic Testing in CI/CD

---

## 🔐 Security Improvements (Production Recommendation)

- Store SSH credentials in Jenkins Credentials Manager
- Avoid hardcoding IP addresses
- Use private networking
- Implement Docker-based deployments
- Use Kubernetes for scalability

---

## 📈 Future Enhancements

- Add Docker build stage
- Add automated testing
- Implement Blue-Green deployment
- Add rollback mechanism
- Integrate with Kubernetes
- Implement GitOps with ArgoCD

---

## 👨‍💻 Author

Sachinkumar H P  
DevOps Engineer

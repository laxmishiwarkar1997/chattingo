# Chattingo – Real-Time Chat Application with CI/CD

![Build Status](https://img.shields.io/jenkins/build?jobUrl=http://jenkins.72.60.111.24.nip.io/job/chattingo-pipeline)
![Frontend Docker Pulls](https://img.shields.io/docker/pulls/laxmi007/chattingo-frontend)
![Backend Docker Pulls](https://img.shields.io/docker/pulls/laxmi007/chattingo-backend)
![Trivy Critical](https://img.shields.io/badge/Trivy-Critical%200-red)
![Trivy High](https://img.shields.io/badge/Trivy-High%200-orange)
![Trivy Medium](https://img.shields.io/badge/Trivy-Medium%200-yellow)
![Trivy Low](https://img.shields.io/badge/Trivy-Low%200-blue)


Chattingo is a fun and dynamic real-time chat application designed to keep you connected effortlessly. Built with a modern tech stack and automated deployment, it demonstrates both cutting-edge frontend/backend development and professional DevOps practices.

---

## 🚀 My Contributions / Additions

* **Dockerization**: Both frontend and backend services are containerized for consistent environments.
* **Jenkins CI/CD Pipeline**: Automated build, scan, push, and deploy process.
* **Trivy Scans**: Security scanning integrated to detect vulnerabilities in source code and Docker images.
* **Deployment on VPS**: Application deployed on a VPS for live access.
* **.env Handling & Multiple Docker Images**: Managed environment variables and separate images for frontend and backend.

---

## 🛠️ Tech Stack

* **Frontend**: React.js
* **Backend**: Spring Boot / Java
* **WebSocket**: Real-time communication
* **Containerization**: Docker & Docker Compose
* **CI/CD**: Jenkins
* **Security**: Trivy
* **Version Control**: GitHub
* **Deployment**: VPS with nip.io domain

---

## 💡 Features

* Real-time messaging between users
* Dockerized services for easy deployment
* Automated CI/CD pipeline with Jenkins
* Vulnerability scanning with Trivy
* Environment variable management with `.env` files
* Separate Docker images for frontend and backend

---

## 📦 Setup & Installation

### Prerequisites

* Docker
* Docker Compose
* Jenkins (optional for CI/CD)
* Git

### Clone the Repository

```bash
git clone https://github.com/laxmishiwarkar1997/chattingo.git
cd chattingo
```

### Environment Configuration

1. **Frontend**: Navigate to `frontend/` and create a `.env` file with required environment variables.
2. **Backend**: Navigate to `backend/` and create a `.env` file with backend configurations.

### Docker Compose

Build and run both services:

```bash
docker-compose up --build
```

---

## ⚙️ CI/CD Pipeline

The Jenkins pipeline automates:

1. **Git Clone**: Pulls latest code.
2. **Image Build**: Builds Docker images for frontend and backend.
3. **Filesystem Scan**: Scans the workspace with Trivy.
4. **Image Scan**: Scans Docker images with Trivy.
5. **Push to Registry**: Pushes images to Docker Hub.
6. **Deploy**: Deploys the application to VPS.

Pipeline is defined in the `Jenkinsfile` in the root directory.
---
## 🌐 Deployment Details

* Hosted on a VPS.  
* Accessible via: [http://72.60.111.24/](http://72.60.111.24/)  
* Docker Hub images:  
  * Frontend: [docker.io/laxmi007/chattingo-frontend](https://hub.docker.com/r/laxmi007/chattingo-frontend)  
  * Backend: [docker.io/laxmi007/chattingo-backend](https://hub.docker.com/r/laxmi007/chattingo-backend)  
---

## 🔒 Security / Quality

* Integrated **Trivy** to scan both source code and Docker images for vulnerabilities.
* Scan reports are archived in Jenkins for audit and review.

---

## 📸 Screenshots / Demo (Optional)

## Screenshots 📸

### Login Page
![Login Page](https://raw.githubusercontent.com/laxmishiwarkar1997/chattingo/main/login.png)

### Chat Interface
![Chat Interface](https://raw.githubusercontent.com/laxmishiwarkar1997/chattingo/main/chat.png)


---

## 🤝 Contributing

Contributions are welcome! Please fork the repository and submit a pull request for review.

---

## 📄 License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

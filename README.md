# 🍲 Cloud Kitchen Web Application (DevOps Project)

## 📌 Project Overview

The **Cloud Kitchen Web Application** is a static food menu website built using HTML and CSS, containerized with Docker, and deployed using a Jenkins CI/CD pipeline on an Nginx web server.

This project demonstrates real-world DevOps practices including **automation, containerization, and continuous deployment**.

---

## 🏗️ Architecture Diagram

```id="avc1sy"
Developer (GitHub)
        ↓
     Jenkins
        ↓
   Build & Deploy
        ↓
      Nginx Server
        ↓
     Browser
```

---

## 🔄 CI/CD Pipeline Flow

```id="1htp43"
1. Developer pushes code to GitHub
2. Jenkins pulls the latest code
3. Jenkins executes pipeline (Jenkinsfile)
4. Installs Nginx (if not available)
5. Deploys HTML, CSS, and images
6. Restarts Nginx
7. Website becomes live
```

---

## 🚀 Features

* 🍛 Food menu UI with images
* 🎨 Responsive design
* 🐳 Docker containerization
* ⚙️ Automated CI/CD using Jenkins
* 🌐 Deployment using Nginx
* ☁️ Hosted on AWS EC2

---

## 🛠️ Tech Stack

* HTML5
* CSS3
* Docker
* Jenkins
* Nginx
* AWS EC2

---

## 📂 Project Structure

```id="ykzj2o"
cloud-kitchen/
│
├── index.html
├── styles.css
├── Dockerfile
├── Jenkinsfile
└── images/
    ├── biryani.jpg
    ├── pongal.jpg
    ├── pulihora.jpg
    └── ragi.jpg
```

---

## 🐳 Docker Setup

### Build Image

```bash
docker build -t cloud-kitchen .
```

### Run Container

```bash
docker run -d -p 80:80 cloud-kitchen
```

---

## ⚙️ Jenkins Pipeline Explanation

The Jenkins pipeline automates deployment:

* Installs Nginx if not present
* Clears existing web files
* Copies latest project files
* Sets permissions
* Restarts Nginx service

---

## 🌐 Deployment URL

```id="8b63yb"
http://<your-ec2-public-ip>
```

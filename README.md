
#  AWS EC2 + Docker: Containerizing and Deploying a Static Website

## 📌 Project Overview

This project demonstrates how to **deploy a static website on an AWS EC2 instance using Docker**, and then **push the Docker image to Docker Hub** for reuse and portability.

The goal of this project is to showcase **cloud deployment, containerization, and basic DevOps practices** through a simple but realistic workflow.

---

## 🛠️ Technologies Used

* **AWS EC2** – Cloud compute service
* **Docker** – Containerization platform
* **Docker Hub** – Image registry
* **Linux (Ubuntu)** – Server operating system
* **Nginx** – Web server (inside Docker container)
* **HTML/CSS** – Static website content

---

## 🏗️ Architecture

```
Local Machine
     ↓
  AWS EC2 
     ↓
Docker Engine
     ↓
Nginx Container
     ↓
Static Website
     ↓
Docker Hub (Image Registry)
```

---

## ⚙️ Project Steps

### 1. Launch an EC2 Instance

* Created an Amazon Linux EC2 instance
* Opened ports **22 (SSH)** and **80 (HTTP)**
* Connected via SSH

---

### 2. Install Docker on EC2

```bash
sudo yum update -y
sudo amazon-linux-extras install docker -y
sudo service docker start
sudo systemctl enable docker
```

### 3. Exit and login back to your ec2 instance.
---

### 4. Create the Dockerfile

 The Dockerfile defines how the static website is packaged into a container.


### 5. Build and Run the Docker Image

e.g 

```bash
docker build -t my-static-website .
docker run -d -p 80:80 my-static-website
```

At this stage, the website becomes accessible via the EC2 public IP address.

---

### 6. Push Image to Docker Hub

```bash
docker login
docker tag my-static-website <dockerhub-username>/my-static-website:latest
docker push <dockerhub-username>/my-static-website:latest
```

This allows the image to be reused or deployed on any system with Docker installed.

---

## ✅ Results

* Static website successfully deployed on AWS EC2
* Application fully containerized using Docker
* Docker image published to Docker Hub
* Deployment is **reproducible and portable**

---

![Alt text](Result.PNG)




## 📚 Key Learnings

* How to deploy applications on **AWS EC2**
* Writing and using a **Dockerfile**
* Running containers in a cloud environment
* Pushing and managing images on **Docker Hub**
* Understanding the value of containerization in DevOps workflows

---






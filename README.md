🚀 Spring MVC CI/CD Deployment on AWS (ECS + ALB)
📌 Project Overview

This project demonstrates a production-grade CI/CD pipeline for a Spring MVC application using GitHub Actions, Docker, SonarQube, Trivy, and AWS ECS.

The pipeline ensures code quality, security scanning, and automated container deployment while keeping cloud costs optimized by running quality tools locally.

🎯 Key Objectives

Automate build, test, and deployment using CI/CD

Enforce code quality using SonarQube

Enforce container security using Trivy

Deploy containers to AWS ECS (Fargate) behind an Application Load Balancer

Follow cost-efficient DevOps best practices

🧰 Technology Stack
Application

Java 21

Spring MVC

Maven

Apache Tomcat

MySQL

DevOps & Cloud

GitHub Actions (CI/CD)

Docker

SonarQube (Local via Docker + ngrok)

Trivy (Container Security)

AWS ECR

AWS ECS (Fargate)

AWS Application Load Balancer (ALB)

🏗️ Architecture Overview
High-Level Architecture Flow
Developer
   ↓
GitHub Repository
   ↓
GitHub Actions (CI/CD)
   ├─ Maven Build & Test
   ├─ SonarQube Code Quality Scan
   ├─ Docker Image Build
   ├─ Trivy Security Scan
   ├─ Push Image to Amazon ECR
   ↓
Amazon ECS (Fargate)
   ↓
Application Load Balancer (ALB)
   ↓
End Users


📷 Architecture Diagram

Add your architecture image here (PNG/JPG)

![CI/CD Architecture](docs/architecture.png)


(Recommended folder: docs/architecture.png)

🔄 CI/CD Pipeline Workflow
1️⃣ Code Commit

Developer pushes code to the main branch

2️⃣ Continuous Integration

Maven builds the application

Unit tests are executed

SonarQube analyzes code quality via a secure ngrok tunnel

3️⃣ Containerization & Security

Docker image is built

Trivy scans the image

Pipeline fails on HIGH or CRITICAL vulnerabilities

4️⃣ Continuous Deployment

Secure image pushed to Amazon ECR

ECS service pulls the image

Application runs as a Fargate task behind ALB

🔐 Security & Quality Controls

No hard-coded secrets

SonarQube quality analysis before deployment

Trivy vulnerability scanning

IAM least-privilege access

Private container registry (ECR)

💰 Cost Optimization Strategy

SonarQube and Trivy run locally (no SaaS cost)

ECS Fargate removes server management

No idle EC2 instances

Pay-only-for-usage model

🌐 Application Access

The application is exposed via AWS Application Load Balancer

Traffic is routed only to healthy ECS tasks

📁 Repository Structure
.
├── .github/workflows/
│   └── ci-cd.yml
├── Docker-files/
│   └── app/Dockerfile
├── src/
├── pom.xml
├── README.md
└── target/

🧪 How to Run Locally
mvn clean package
docker build -t spring-mvc-app:latest .
docker run -d -p 8083:8080 spring-mvc-app:latest


Access:

http://localhost:8083

🧠 Interview Explanation (Short)

“This project implements an end-to-end CI/CD pipeline where Spring MVC code is built and quality-checked using SonarQube, containerized and scanned with Trivy, stored in AWS ECR, and deployed on ECS Fargate behind an Application Load Balancer.”

🚀 Future Enhancements

HTTPS using ACM

RDS MySQL integration

Auto Scaling for ECS services

Terraform-based infrastructure

Multi-environment pipelines (dev/prod)

👨‍💻 Author

Giri
DevOps Engineer | AWS | CI/CD | Docker | Kubernetes
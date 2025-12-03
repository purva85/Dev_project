End-to-End DevOps Automation for Java Web Application

This project demonstrates a fully automated CI/CD pipeline for deploying a Spring Boot (STS) web application on an AWS EC2 instance using Jenkins, Terraform, and Git.
The workflow eliminates all manual deployments and provisions infrastructure automatically, ensuring fast, reliable, and repeatable releases.

Project Overview

This repository showcases a complete DevOps pipeline:
Code Management: Git + GitHub
CI Pipeline: Jenkins (Build → Test → Package)
Infrastructure as Code: Terraform automation for VPC + EC2
Deployment: WAR file deployed to Tomcat on EC2
Cloud Monitoring: AWS CloudWatch
Security: Key-based SSH authentication
Automation: Zero manual intervention after code push

Pipeline Stages
1️⃣ Source Stage
GitHub repository linked to Jenkins
Webhook triggers pipeline on push

2️⃣ Build Stage
Maven compiles the project and generates .war
Unit tests executed (if added)

3️⃣ Infrastructure Stage
Terraform executes:
VPC
Subnets
Security groups (port 22, 8080)
EC2 instance
SSH keys configured for deployment

4️⃣ Deploy Stage
Jenkins copies WAR → EC2 (Tomcat webapps/)
Tomcat service restart
Application available on browser using EC2 public IP


How to Run This Project
1. Clone the Repository
git clone https://github.com/purva85/name_.git
cd DevOps-Automation

2. Configure Terraform
cd terraform
terraform init
terraform apply -auto-approve

3. Run Jenkins Pipeline
Import the repository into Jenkins
Use provided Jenkinsfile
Run pipeline → builds & deploys automatically

4. Access Application

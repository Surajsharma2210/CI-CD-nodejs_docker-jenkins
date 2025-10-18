
# CI/CD Pipeline for Node.js App using Jenkins & Docker on AWS EC2

## Overview
This project automates build, test, and deployment of a Node.js web app using Jenkins and Docker. It runs completely on AWS EC2 Free Tier.

## Stack
- Node.js + Express
- Docker
- Jenkins
- AWS EC2
- GitHub Webhooks

## How to Run
1. Launch an EC2 instance (t2.micro, Ubuntu).
2. Install Jenkins and Docker.
3. Create a Jenkins pipeline (Pipeline from SCM).
4. Push code to GitHub → Jenkins auto-triggers → App runs on EC2 port 3000.

Test URL: http://<EC2-PUBLIC-IP>:3000

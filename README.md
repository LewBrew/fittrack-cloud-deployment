# FitTrack AWS Cloud Deployment

A cloud-deployed version of the FitTrack MERN fitness tracking application hosted on AWS EC2. This repository focuses on deploying, configuring, and managing the application in a Linux cloud server environment using Nginx, PM2, and MongoDB Atlas.

Original FitTrack application repository:

https://github.com/LewBrew/fitness-tracker

---

# Project Overview

This project demonstrates deploying a full-stack MERN application to the cloud using AWS infrastructure and Linux server configuration tools.

The focus of this repository is cloud deployment, server management, and production-style hosting rather than application feature development.

---

# Cloud Deployment Features

- AWS EC2 Ubuntu Server Deployment
- SSH Key Authentication
- React Frontend Production Build
- Express Backend Hosting
- Nginx Reverse Proxy Configuration
- PM2 Process Management
- MongoDB Atlas Cloud Database
- Public Web Hosting
- Linux Server Administration
- Environment Variable Configuration

---

# Tech Stack

## Cloud / Infrastructure

- AWS EC2
- Ubuntu Linux
- Nginx
- PM2
- SSH

## Frontend

- React
- Vite
- React Router

## Backend

- Node.js
- Express.js
- Mongoose
- JWT Authentication

## Database

- MongoDB Atlas

---

# Deployment Architecture

```text
User Browser
      ↓
Nginx Web Server
      ↓
React Frontend + Express Backend
      ↓
MongoDB Atlas
```

---

# Deployment Process

## 1. Provisioned AWS EC2 Instance

Created an Ubuntu EC2 instance and configured security group rules for SSH, HTTP, HTTPS, and application traffic.

## 2. Connected Through SSH

Connected securely using a `.pem` SSH key.

```bash
ssh -i fittrack-key.pem ubuntu@your-ec2-ip
```

## 3. Installed Server Dependencies

Installed Node.js, npm, Git, Nginx, and PM2 on the Ubuntu server.

## 4. Configured MongoDB Atlas

Connected the backend to a cloud-hosted MongoDB Atlas cluster using environment variables.

## 5. Built React Frontend

Generated a production frontend build using Vite.

```bash
npm run build
```

## 6. Configured Nginx

Configured Nginx to serve the React frontend and route API requests to the Express backend.

## 7. Managed Backend with PM2

Used PM2 to keep the backend running persistently and restart automatically after crashes or server reboots.

---

# Example Deployment Commands

## Clone Repository

```bash
git clone https://github.com/LewBrew/fitness-tracker.git
cd fitness-tracker
```

## Install Dependencies

```bash
npm install
cd client
npm install
```

## Build Frontend

```bash
npm run build
```

## Start Backend with PM2

```bash
pm2 start server.js --name fittrack-backend
pm2 save
pm2 startup
```

## Restart Nginx

```bash
sudo nginx -t
sudo systemctl restart nginx
```

---

# Screenshots

## AWS EC2 Instance

![AWS EC2](screenshots/aws-ec2.png)

## MongoDB Atlas Cluster

![MongoDB Atlas](screenshots/mongo-cluster.png)

## PM2 Backend Status

![PM2 Status](screenshots/pm2-status.png)

## PM2 Application Logs

![PM2 Logs](screenshots/pm2-logs.png)

## Application Login

![Application Login](screenshots/dashboard.png)

## Admin Dashboard

![Admin Dashboard](screenshots/admin-panel.png)

---

# Difference From Original FitTrack Repository

The original FitTrack repository focuses on application development and MERN stack functionality such as authentication, workout tracking, goal tracking, admin functionality, MongoDB schemas, and frontend UI.

This repository focuses specifically on cloud deployment and infrastructure management:

- AWS EC2 hosting
- Linux server setup
- PM2 process management
- Nginx configuration
- MongoDB Atlas integration
- Public deployment configuration

---

# Security Notes

Sensitive files are excluded from this repository:

- `.env`
- `.pem` SSH keys
- MongoDB credentials
- connection strings
- `node_modules`

---

# Skills Demonstrated

- AWS EC2 Deployment
- Linux Server Administration
- Nginx Reverse Proxy Setup
- PM2 Process Management
- Cloud Database Integration
- MERN Stack Deployment
- SSH Configuration
- Environment Variable Management
- Production Hosting Workflow
- Full-Stack Cloud Deployment

---

# Future Improvements

- HTTPS / SSL Certificate
- Custom Domain Name
- Docker Containerization
- CI/CD Pipeline
- AWS Load Balancer
- CloudWatch Monitoring
- Improved Frontend Error Handling
- Restrict MongoDB Atlas access to only the EC2 server IP

---

# Related Repository

Original FitTrack MERN Application:

https://github.com/LewBrew/fitness-tracker

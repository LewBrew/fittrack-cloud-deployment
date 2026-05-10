# FitTrack AWS Cloud Deployment

A cloud-deployed version of the FitTrack MERN fitness tracking application hosted on AWS EC2. This repository focuses on deploying, configuring, and managing the application in a production-style Linux server environment using Nginx, PM2, and MongoDB Atlas.

The original application code is based on the FitTrack MERN project: https://github.com/LewBrew/fitness-tracker

---

## Project Purpose

This repository documents the cloud deployment process for FitTrack rather than focusing only on application development.

The main goal was to take an existing full-stack MERN application and deploy it publicly using AWS infrastructure, server configuration, process management, and cloud database integration.

---

## Cloud Deployment Features

- AWS EC2 Ubuntu Server Deployment
- SSH Key-Based Server Access
- Node.js Backend Hosting
- React Production Build Deployment
- Nginx Web Server Configuration
- Nginx Reverse Proxy Routing
- PM2 Backend Process Management
- MongoDB Atlas Cloud Database Integration
- Security Group Configuration
- Public Web Application Hosting
- Linux Server Environment Setup

---

## Deployment Architecture

The application uses a cloud-hosted deployment architecture.

### Frontend

- React application built with Vite
- Production files generated using `npm run build`
- Static frontend served through Nginx

### Backend

- Node.js and Express.js API
- Managed with PM2 for persistent runtime
- Runs on the EC2 instance behind Nginx routing

### Database

- MongoDB Atlas cloud database
- Mongoose models used for structured application data
- Remote database connection configured through environment variables

### Server Infrastructure

- AWS EC2 Ubuntu instance
- Nginx as the public-facing web server
- PM2 used to keep the backend running after terminal/session closure

---

## Tech Stack

### Cloud / Infrastructure

- AWS EC2
- Ubuntu Linux
- Nginx
- PM2
- SSH

### Frontend

- React
- Vite
- React Router
- CSS

### Backend

- Node.js
- Express.js
- Mongoose
- JWT Authentication
- bcrypt

### Database

- MongoDB Atlas

---

## Application Screenshots

### AWS EC2 Instance

![AWS EC2 Instance](screenshots/aws-ec2.png)

### MongoDB Atlas Cluster

![MongoDB Atlas Cluster](screenshots/mongo-cluster.png)

### PM2 Backend Process

![PM2 Backend Process](screenshots/pm2-status.png)

### Dashboard

![Login Page](screenshots/dashboard.png)

### Admin Panel

![Admin Panel](screenshots/admin-panel.png)

---

## Deployment Process

### 1. Provisioned AWS EC2 Instance

Created an Ubuntu-based EC2 instance and configured inbound security group rules for SSH, HTTP, HTTPS, and backend testing.

### 2. Connected Through SSH

Used a `.pem` key file to securely access the EC2 instance through the terminal.

### 3. Installed Server Dependencies

Installed required server tools including:

- Node.js
- npm
- Git
- Nginx
- PM2

### 4. Cloned and Configured Application

Cloned the FitTrack application repository onto the EC2 instance and configured the backend environment variables for MongoDB Atlas.

### 5. Connected MongoDB Atlas

Configured MongoDB Atlas network access and connected the Express backend to the cloud database.

### 6. Built React Frontend

Generated the production frontend build using:

```bash
npm run build

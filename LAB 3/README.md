# AWS Full-Stack Cloud Lab: Scalable Image Upload & Processing Application

This project demonstrates the deployment of a scalable web application on AWS that allows users to upload images, store them in S3, automatically trigger a Lambda function to resize them, store metadata in RDS, share file storage through EFS, and serve the application behind a Load Balancer and CloudFront with domain integration.

---

## 🚀 **Project Architecture Overview**

This lab includes:

- VPC with 3 Public Subnets
- EC2 as PHP Application Servers (Auto-Scaled)
- S3 for Original + Resized Image Storage
- Lambda for Image Resizing
- IAM Roles for Service Permissions
- EFS for Shared File Storage Between EC2 Instances
- RDS (MySQL) for Visitor Data Storage
- Application Load Balancer + Target Groups
- CloudFront CDN Distribution
- Route53 for DNS Mapping

---

## 🌐 **Core Features**

✔ Upload images via web form  
✔ Store uploaded images in S3 (original)  
✔ Lambda generates 100×100 resized images  
✔ Display resized images from S3  
✔ Store user data in RDS (MySQL)  
✔ Share `/var/www/html` via EFS across EC2 Auto-Scaling Group  
✔ Highly-available through Load Balancer & Auto-Scaling  
✔ Public access via CloudFront + Route53 domain

---

## 🧱 **AWS Services Used**

| Service | Purpose |
|---|---|
| VPC | Network configuration |
| EC2 | Application servers |
| S3 | Original + resized image storage |
| Lambda | Image resizing |
| IAM | Permissions control |
| EFS | Shared FS for images & PHP app |
| RDS | MySQL database |
| ALB | Load balancing between EC2 nodes |
| Auto Scaling | HA and self-healing |
| CloudFront | Global content delivery |
| Route53 | DNS record management |

---

## 🏗️ **Project Steps (High-Level Summary)**

### **1. VPC Setup**
- Create a VPC containing **3 public subnets**

### **2. S3 Buckets**
- Bucket 1: `projectname` → stores original images inside `/images`
- Bucket 2: `projectname-resized` → stores resized images  
- Configure:
  - ACLs
  - Bucket Policy for public access
  - CORS allowing `GET`, `PUT`, `POST`

### **3. IAM Roles**
Created:
| Role Name | Service | Policy |
|---|---|---|
| `Lambda-S3` | Lambda | AWSLambdaExecute |
| `EC2-S3` | EC2 | AmazonS3FullAccess |

### **4. Lambda Image Resizing**
- Runtime: **Node.js 20**
- Trigger: S3 `All Object Create Events`
- Action:
  - Reads image from `eminproject-aws/images`
  - Resizes to `100x100`
  - Stores into `eminproject-aws-resized`

### **5. Security Group**
- Name: `Project-SecGroup`
- Inbound:
  - HTTP/80 → 0.0.0.0/0
  - SSH/22 → 0.0.0.0/0

### **6. EC2 Template Instance**
- AMI: Amazon Linux 2
- Type: t2.micro
- Role: `EC2-S3`
- Security Group: `Project-SecGroup`
- Installed Packages:
  - `httpd`, `php 8.4`, `mysql`


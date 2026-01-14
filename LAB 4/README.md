# ☁️ Huawei Cloud High-Availability LAMP Deployment Lab

This project demonstrates the deployment of a scalable and highly available web application environment running on a **LAMP stack** (Linux, Apache, MySQL, PHP) using **Huawei Cloud** services.  
The architecture separates database and application tiers, supports automatic scaling, and balances traffic across multiple ECS instances.

---

## 🚀 Project Architecture Overview

This lab includes:

- VPC with subnets & routing
- ECS instances for Web (Apache + PHP)
- ECS instance for Database (MySQL)
- Elastic Load Balancer (ELB)
- Auto Scaling policies for ECS
- Cloud Eye for metrics & monitoring
- Security Group rules
- Public Access via Load Balancer

---

## 🌐 Core Features

✔ LAMP stack deployment on Huawei Cloud  
✔ Separate ECS nodes for Database & Web services  
✔ Automatic scaling of Web ECS nodes based on traffic  
✔ Load-balanced incoming HTTP requests via ELB  
✔ Continuous monitoring via Cloud Eye  
✔ Public accessibility over the internet  

---

## 🧱 Huawei Services Used

| Service | Purpose |
|---|---|
| VPC | Network topology & subnets |
| ECS | LAMP web servers and DB node |
| ELB | Traffic load balancing |
| Auto Scaling | Adjust ECS count based on demand |
| Cloud Eye | Monitoring & metric visualization |
| Security Groups | Firewall & inbound rules |

---

## 🏗️ Project Steps (High-Level Summary)

### **1. VPC Setup**
- Create a VPC and required Subnets
- Configure routing & network access
- Assign Security Groups

### **2. ECS Deployment**
Deploy the compute resources:
- ECS #1 → Web Server (Apache + PHP)
- ECS #2 → Database Server (MySQL)

Installed Components:
- Apache (httpd)
- PHP
- MySQL (on DB ECS)

### **3. LAMP Configuration**
Configure:
- Apache virtual hosts
- PHP runtime
- MySQL database authentication
- Application DB connection

Verify:
- PHP info page
- MySQL connectivity from Web ECS

### **4. High Availability Setup**
Configure high availability architecture:
- Create Elastic Load Balancer
- Register Web ECS instances
- Configure Auto Scaling policies:
  - Scale Out when CPU/traffic increases
  - Scale In when load decreases

### **5. Public Website Validation**
- Access website via ELB Public Endpoint
- Verify balanced traffic distribution
- Confirm database read/write operations

### **6. Monitoring Resources**
Monitor using **Cloud Eye**:
- ECS CPU/Memory usage
- Network throughput
- Scaling activities
- Load balancer performance

---

## 🔐 Security Group Configuration

Example Inbound Rules:

| Protocol | Port | Source |
|---|---|---|
| HTTP | 80 | 0.0.0.0/0 |
| SSH | 22 | Your IP |
| MySQL | 3306 | Web ECS CIDR |

Outbound: allow all (default)

---

## 🧩 Architecture Highlights

- **Service Separation** — DB & App nodes run independently
- **Scalability** — Auto Scaling adjusts ECS count dynamically
- **Traffic Distribution** — ELB balances client requests
- **Observability** — Cloud Eye metrics and logs ensure visibility
- **Fault Tolerance** — Eliminates dependency on a single instance

---

## 📦 Final Result

After completing this lab, you will have:

✔ A scalable multi-ECS LAMP environment  
✔ Automatic load-balancing and scaling  
✔ Resource monitoring and metrics visibility  
✔ Public-facing application endpoint  
✔ Demonstration of production-grade HA architecture

---

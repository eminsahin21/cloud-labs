☁️ Huawei Cloud High-Availability LAMP Deployment Lab

This project demonstrates the deployment of a scalable and highly available web application environment running on a LAMP stack (Linux, Apache, MySQL, PHP) using Huawei Cloud services.
The architecture separates database and application tiers, supports automatic scaling, and balances traffic across multiple ECS instances.

🚀 Project Architecture Overview

This lab includes:

VPC with subnets & routing

ECS instances for Web (Apache + PHP)

ECS instance for Database (MySQL)

Elastic Load Balancer (ELB)

Auto Scaling policies for ECS

Cloud Eye for metrics & monitoring

Security Group rules

Public Access via Load Balancer

🌐 Core Features

✔ LAMP stack deployment on Huawei Cloud
✔ Separate ECS nodes for Database & Web services
✔ Automatic scaling of Web ECS nodes based on traffic
✔ Load-balanced incoming HTTP requests via ELB
✔ Continuous monitoring via Cloud Eye
✔ Public accessibility over the internet

🧱 Huawei Services Used
Service	Purpose
VPC	Network topology & subnets
ECS	LAMP web servers and DB node
ELB	Traffic load balancing
Auto Scaling	Adjust ECS count based on demand
Cloud Eye	Monitoring & metric visualization
Security Groups	Firewall & inbound rules
🏗️ Project Steps (High-Level Summary)
1. VPC Setup

Create a VPC and required Subnets

Configure routing & network access

Assign Security Groups

2. ECS Deployment

ECS #1 (Web Server)

ECS #2 (Database Server)

Install & configure:

Apache (httpd)

PHP

MySQL (on DB ECS)

3. LAMP Configuration

Install LAMP packages

Configure PHP + Apache

Connect App → MySQL DB

Test DB connectivity

4. High Availability via ELB + AS

Create Elastic Load Balancer

Register Web ECS instances

Configure Auto Scaling:

Scale Out on high CPU/traffic

Scale In on low traffic

5. Public Website Validation

Access the website via ELB public endpoint

Verify request distribution between nodes

6. Monitoring Resources

Use Cloud Eye to monitor:

CPU Usage

Network traffic

Scaling actions

ECS health

🔐 Security Group Configuration

Inbound Rules Example:

Protocol	Port	Source
HTTP	80	0.0.0.0/0
SSH	22	Your IP
MySQL	3306	Web ECS CIDR

Outbound: allow all (default)

🧩 Architecture Highlights

Service Separation: DB & App nodes run independently

Scalability: Auto Scaling adjusts ECS count

Traffic Distribution: ELB balances HTTP requests

Observability: Cloud Eye + logs

Fault Tolerance: No single web node dependency
# ECS Lifecycle & Image Management Lab (Huawei Cloud)

This lab demonstrates core **Elastic Cloud Server (ECS)** lifecycle operations and **custom image management** on **Huawei Cloud**.  
The goal is to understand how ECS instances are created, modified, and converted into reusable system disk images for both **Windows** and **Linux** environments.

---

## 🧪 Objectives and Requirements

- Create and log in to an ECS
- Modify ECS specifications (CPU, RAM)
- Create a Virtual Private Cloud (VPC)
- Create a **Windows system disk image** from an ECS
- Create a **Linux system disk image** from an ECS
- Modify and share custom images

---

## 🛠️ Technologies & Services Used

- **Huawei Cloud**
  - Elastic Cloud Server (ECS)
  - Virtual Private Cloud (VPC)
  - Image Management Service (IMS)
- Operating Systems
  - Windows Server
  - Linux (e.g. CentOS / Ubuntu)

---

## 🔄 Lab Workflow Overview

1. **VPC Creation**
   - Created a custom VPC with subnet and security group
   - Configured basic network access rules

2. **ECS Lifecycle Management**
   - Created ECS instances inside the VPC
   - Logged in to ECS (RDP for Windows, SSH for Linux)
   - Modified ECS specifications

3. **Image Creation**
   - Created a **Windows system disk image** from a running ECS
   - Created a **Linux system disk image** from a running ECS

4. **Image Management**
   - Modified image metadata
   - Shared custom images with other accounts/projects

---

## 🧠 Key Learnings

- Understanding ECS lifecycle operations
- Difference between Windows and Linux system disk images
- How custom images improve deployment speed and consistency
- Image sharing for multi-project or multi-account environments

---

## 📌 Notes

- Hypervisor and underlying infrastructure are managed by Huawei Cloud (IaaS model)
- Images are created from system disks, not data disks
- ECS must be stopped or in a consistent state before image creation

---

## 📄 Author

**Mehmet Emin Şahin**  
Computer Engineer  
Interested in Cloud Computing, Backend Development, and Mobile Applications


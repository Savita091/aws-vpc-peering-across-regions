# AWS Cross-Region VPC Peering with Multi-Subnet Architecture

This project demonstrates secure private-to-private communication between two VPCs
located in different AWS regions using VPC peering, with Bastion (Jump Server) access.

---

## 🌍 Regions Used
- **Mumbai (ap-south-1)**
- **Singapore (ap-southeast-1)**

---

## 🔹 VPC & Subnet Structure

| Region | VPC CIDR | Public Subnets (3) | Private Subnets (3) |
|--------|----------|------------------|-------------------|
| Mumbai | 10.0.0.0/16 | 10.0.1.0/24, 10.0.5.0/24, 10.0.6.0/24 | 10.0.2.0/24, 10.0.3.0/24, 10.0.4.0/24 |
| Singapore | 192.168.0.0/16 | 192.168.1.0/24, 192.168.5.0/24, 192.168.6.0/24 | 192.168.2.0/24, 192.168.3.0/24, 192.168.4.0/24 |

---

## 🔐 EC2 Instances
| Location | Instance Type | OS | Subnet | Purpose |
|---------|---------------|----|--------|---------|
| Mumbai | t2.micro | Amazon Linux 2 | Public Subnet-3 | Jump Server (Bastion Host) |
| Mumbai | t2.micro | Amazon Linux 2 | Private Subnet-3 | Private EC2 |
| Singapore | t2.micro | Amazon Linux 2 | Public Subnet-3 | Jump Server |
| Singapore | t2.micro | Amazon Linux 2 | Private Subnet-3 | Private EC2 |

---

## 🔄 VPC Peering Configuration
- Peering connection created between private networks
- Route tables updated accordingly
- No Internet required for private communication

---

## 🧪 Connectivity Testing (Ping)

| Source | Destination | Result |
|--------|------------|--------|
| Mumbai Private EC2 | Singapore Private EC2 | ✅ Success |
| Singapore Private EC2 | Mumbai Private EC2 | ✅ Success |

Ping logs are included in `connectivity-test/` folder

---

## 🖼 Architecture Diagram
See: **updated-architecture-diagram.png**

---

## 🎯 Project Highlights
✔ Cross-region VPC peering  
✔ 3-tier subnet design (Public + Private Separation)  
✔ Bastion Host SSH security model  
✔ End-to-end private connectivity validated  
✔ Demonstrates strong AWS networking skills  

---

## 🚀 Skills Demonstrated
- VPC Design & Subnetting  
- Security Groups & Routing  
- Bastion Host SSH Access  
- VPC Peering  
- Linux Networking Commands  


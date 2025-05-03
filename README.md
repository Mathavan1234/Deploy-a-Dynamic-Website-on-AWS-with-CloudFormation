# 🚀 Deploy a Dynamic Website on AWS with CloudFormation

This repository provides a complete guide to deploying a scalable and secure dynamic web application infrastructure using **AWS CloudFormation**. It automates provisioning of VPC, Subnets, NAT Gateways, Load Balancers, RDS, Auto Scaling, Route 53, and Security Groups across multiple Availability Zones.

---

## 📌 Overview

This project includes the following major components:

- VPC with public and private subnets (2 AZs)
- Internet Gateway and route configuration
- NAT Gateway setup with Elastic IPs
- RDS database provisioned from a snapshot
- Application Load Balancer (ALB) with Target Group
- Auto Scaling Group (ASG) with CloudWatch policies
- Route 53 record to host the dynamic website
- Security Groups for ALB, Web Server, Bastion Host, and Database

---

## 🧱 Infrastructure Breakdown

### 1. **VPC and Subnet Configuration**
- VPC creation
- Public and private subnets in 2 AZs
- Internet Gateway attachment
- Public route table for internet access

### 2. **Security Groups**
- ALB SG
- Web Server SG
- Bastion Host SG (for SSH access)
- Database SG

### 3. **NAT Gateway Setup**
- Two Elastic IPs
- Two NAT Gateways in separate AZs
- Private Route Tables for outbound internet access

### 4. **RDS Setup**
- RDS instance creation from a DB snapshot
- Parameters defined for DB name, snapshot ID, instance class
- Created in private subnets with database security group

### 5. **Application Load Balancer (ALB)**
- ALB and Target Group across public subnets
- Listener rules to forward requests
- Exported outputs for integration

### 6. **Auto Scaling Group**
- Launch Template for EC2 instances
- Scaling policies and CloudWatch alarms
- ALB target registration and health checks

### 7. **Route 53**
- Hosted Zone configuration
- Record Set to point domain to ALB DNS name

---

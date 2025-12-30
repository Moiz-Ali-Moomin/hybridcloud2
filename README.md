# ☁️ AWS WordPress & MySQL Infrastructure using Terraform

## 📌 Overview
This project provisions a **basic AWS infrastructure using Terraform** to deploy:
- A **WordPress web server** in a public subnet
- A **MySQL database server** in a private subnet
- Supporting networking components (VPC, subnets, route tables, security groups)

The goal is to demonstrate **Infrastructure as Code (IaC)** fundamentals and **AWS networking best practices** using Terraform.

---

## 🧠 Problem Statement
Manually creating AWS resources via the console is:
- Time-consuming
- Error-prone
- Hard to reproduce consistently

This project solves that by:
- Defining the complete AWS setup in Terraform
- Separating public and private resources
- Applying controlled access using security groups

---

## 🏗️ Architecture & Workflow
Internet
↓
Internet Gateway
↓
Public Subnet (ap-south-1a)
└── WordPress EC2 (HTTP + SSH)
↓
Private Subnet (ap-south-1b)
└── MySQL EC2 (Private Access)

yaml
Copy code

---

## 🛠️ Tech Stack
- **Cloud Provider:** AWS
- **Infrastructure as Code:** Terraform
- **Compute:** EC2
- **Networking:** VPC, Subnets, Route Tables
- **Security:** Security Groups
- **Application:** WordPress
- **Database:** MySQL

---

## ⚙️ Key Features
- Custom VPC with DNS hostnames enabled
- Public subnet with internet access
- Private subnet for database isolation
- Internet Gateway and routing for public subnet
- Security groups controlling SSH, HTTP, and MySQL access
- Automated EC2 provisioning using Terraform

---

## 📂 Project Structure

```text
terraform-aws-wordpress-mysql/
├── main.tf
└── README.md
All infrastructure resources are defined in a single Terraform file for simplicity.

🚀 How to Run the Project

1️⃣ Prerequisites
AWS account

IAM user with EC2 & VPC permissions

Terraform installed

AWS CLI configured

Existing EC2 key pair (key53)

2️⃣ Clone the repository
bash
Copy code
git clone https://github.com/your-username/terraform-aws-wordpress-mysql.git
cd terraform-aws-wordpress-mysql

3️⃣ Initialize Terraform
bash
Copy code
terraform init

4️⃣ Review execution plan
bash
Copy code
terraform plan

5️⃣ Apply infrastructure
bash
Copy code
terraform apply

📊 Outcome / Results

WordPress EC2 instance deployed in public subnet

MySQL EC2 instance deployed in private subnet

Network isolation between application and database

Infrastructure reproducible using Terraform

🧪 What I Learned

Creating VPCs and subnets using Terraform

Managing AWS route tables and gateways

Applying security groups for access control

Provisioning EC2 instances via IaC

Structuring basic cloud architectures

🔮 Future Enhancements

Add NAT Gateway for private subnet outbound access

Replace EC2-based MySQL with Amazon RDS

Add Bastion host for secure SSH access

Use Terraform variables and outputs

Add Load Balancer for WordPress

Split configuration into multiple Terraform files

# 🚀 Terraform + Jenkins Enterprise CI/CD Pipeline

![Terraform](https://img.shields.io/badge/Terraform-IaC-623CE4?logo=terraform&logoColor=white)
![Jenkins](https://img.shields.io/badge/Jenkins-CI%2FCD-D24939?logo=jenkins&logoColor=white)
![AWS](https://img.shields.io/badge/AWS-Cloud-232F3E?logo=amazonaws&logoColor=white)
![EKS](https://img.shields.io/badge/Amazon-EKS-FF9900?logo=amazonaws&logoColor=white)
![Enterprise](https://img.shields.io/badge/Enterprise-Grade-success)

------------------------------------------------------------------------

## 🧠 Project Overview

This project demonstrates a production-style Infrastructure-as-Code
(IaC) CI/CD pipeline using:

-   Terraform for AWS infrastructure provisioning
-   Jenkins Declarative Pipeline for automation
-   Secure credential management
-   Parameterized Apply / Destroy execution
-   Manual approval gates
-   Amazon EKS cluster provisioning

------------------------------------------------------------------------

## 🏗 Architecture Workflow

Developer → GitHub → Jenkins → Terraform Init → Validate → Plan →
Approval → Apply/Destroy → AWS (VPC + EKS)

------------------------------------------------------------------------

## ⚙️ What This Project Does

✔ Automates Terraform execution via Jenkins\
✔ Provisions AWS networking stack (VPC, Subnets, NAT, IGW)\
✔ Deploys Amazon EKS cluster\
✔ Implements approval workflow before infrastructure changes\
✔ Supports controlled infrastructure destruction\
✔ Secures AWS credentials using Jenkins credential store\
✔ Archives Terraform plan artifacts

------------------------------------------------------------------------

## 📦 Infrastructure Components

-   VPC
-   Public & Private Subnets
-   NAT Gateway
-   Route Tables
-   Security Groups
-   IAM Roles & Policies
-   KMS Encryption
-   Amazon EKS Cluster
-   Managed Node Group

------------------------------------------------------------------------

## 🔄 Pipeline Capabilities

  Feature              Status
  -------------------- --------
  Terraform Init       ✅
  Terraform Validate   ✅
  Terraform Plan       ✅
  Manual Approval      ✅
  Apply                ✅
  Destroy              ✅
  Secure Credentials   ✅
  Artifact Archiving   ✅

------------------------------------------------------------------------

## 🛠 Tech Stack

Terraform • Jenkins • AWS • Amazon EKS • GitHub • Amazon Linux

------------------------------------------------------------------------

## 👨‍💻 Author

Avik Kumar Banerjee\
Cloud / DevOps Engineer\
AWS \| Terraform \| Jenkins \| Kubernetes \| CI/CD

------------------------------------------------------------------------

⭐ Enterprise-ready Infrastructure Automation Pipeline

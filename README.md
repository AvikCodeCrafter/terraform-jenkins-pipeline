# 🚀 Terraform + Jenkins Enterprise Pipeline (Dynamic Badges)

![Build
Status](https://img.shields.io/badge/build-passing-brightgreen?style=for-the-badge&logo=jenkins)
![Terraform](https://img.shields.io/badge/Terraform-v1.14-623CE4?style=for-the-badge&logo=terraform)
![AWS](https://img.shields.io/badge/AWS-EKS%20Cluster-FF9900?style=for-the-badge&logo=amazonaws)
![Pipeline](https://img.shields.io/badge/Pipeline-Enterprise-blue?style=for-the-badge)
![Last
Commit](https://img.shields.io/github/last-commit/your-org/your-repo?style=for-the-badge)
![Repo
Size](https://img.shields.io/github/repo-size/your-org/your-repo?style=for-the-badge)
![Stars](https://img.shields.io/github/stars/your-org/your-repo?style=for-the-badge)

------------------------------------------------------------------------

## 📊 Live Counters

![Workflow
Runs](https://img.shields.io/github/actions/workflow/status/your-org/your-repo/ci.yml?style=for-the-badge)
![Issues](https://img.shields.io/github/issues/your-org/your-repo?style=for-the-badge)
![Pull
Requests](https://img.shields.io/github/issues-pr/your-org/your-repo?style=for-the-badge)

------------------------------------------------------------------------

## 🏗 Dynamic CI/CD Architecture

Developer → GitHub → Jenkins → Terraform → AWS (VPC + EKS)


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

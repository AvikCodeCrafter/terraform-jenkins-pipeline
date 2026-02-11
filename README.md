# 🚀 Enterprise Infrastructure Automation

## Terraform + Jenkins CI/CD Pipeline on AWS

![Terraform](https://img.shields.io/badge/Terraform-v1.14-623CE4?style=for-the-badge&logo=terraform&logoColor=white)
![Jenkins](https://img.shields.io/badge/Jenkins-Pipeline-D24939?style=for-the-badge&logo=jenkins&logoColor=white)
![AWS](https://img.shields.io/badge/AWS-EKS%20%7C%20VPC-FF9900?style=for-the-badge&logo=amazonaws&logoColor=white)
![IaC](https://img.shields.io/badge/Infrastructure-as--Code-Enterprise-blue?style=for-the-badge)

------------------------------------------------------------------------

## 📌 Project Overview

This project demonstrates a production-grade Infrastructure as Code
(IaC) pipeline using:

-   🔹 Terraform (modular infrastructure provisioning)
-   🔹 Jenkins (CI/CD orchestration)
-   🔹 AWS (EKS, VPC, IAM, Security Groups)
-   🔹 Enterprise approval & governance workflow

It automates the complete AWS infrastructure lifecycle:

✔ Plan\
✔ Manual Approval\
✔ Apply\
✔ Controlled Destroy

------------------------------------------------------------------------

## 🏗 Architecture Overview

![Terraform Jenkins Pipeline Tech-Stack](image.svg)

`Terraform-Jenkins-Animated-Pipeline.svg`

![Terraform Jenkins Pipeline](Terraform-Jenkins-Animated-Pipeline.svg)

------------------------------------------------------------------------

## 🔹 End-to-End Workflow

1️⃣ Developer pushes Terraform code to GitHub\
2️⃣ Jenkins pipeline triggers\
3️⃣ Terraform initializes backend & providers\
4️⃣ Plan is generated and archived\
5️⃣ Manual approval gate enforces governance\
6️⃣ Terraform Apply provisions infrastructure\
7️⃣ Optional Destroy stage removes resources safely

------------------------------------------------------------------------

## 🧱 Infrastructure Components Provisioned

-   ✅ VPC (Public & Private Subnets)
-   ✅ NAT Gateway
-   ✅ Internet Gateway
-   ✅ Security Groups
-   ✅ IAM Roles & Policies
-   ✅ KMS Encryption
-   ✅ Amazon EKS Cluster
-   ✅ Managed Node Groups

------------------------------------------------------------------------

## 🔐 Enterprise Governance Controls

-   🔒 Manual approval before Apply
-   🔒 Parameterized action (apply / destroy)
-   🔒 Secure AWS credentials in Jenkins
-   🔒 Terraform state locking
-   🔒 Modular Terraform architecture
-   🔒 Version-pinned providers

------------------------------------------------------------------------

## 🧩 Pipeline Capabilities

-   Workspace cleanup
-   Secure credential injection
-   Terraform validation
-   Plan artifact archiving
-   Approval-based promotion
-   Controlled destroy mechanism
-   Failure handling & post-stage reporting

------------------------------------------------------------------------

## 📊 CI/CD Maturity Alignment

  Level     Capability                          Status
  --------- ----------------------------------- --------
  Level 1   Scripted IaC                        ✅
  Level 2   CI Validation                       ✅
  Level 3   Approval Governance                 ✅
  Level 4   Modular Infrastructure              ✅
  Level 5   Enterprise Pipeline Orchestration   ✅

------------------------------------------------------------------------

## 🚀 Key Achievements

-   Designed enterprise-grade Terraform pipeline\
-   Provisioned secure AWS EKS infrastructure\
-   Implemented approval-based governance\
-   Automated full infrastructure lifecycle\
-   Integrated CI/CD with Infrastructure as Code

------------------------------------------------------------------------

## 👨‍💻 Author

**Avik Banerjee**\
Cloud \| DevOps \| Infrastructure Automation Engineer

------------------------------------------------------------------------

## ⭐ Resume Highlight

Built and deployed an enterprise-grade Infrastructure Automation
pipeline using Terraform and Jenkins, enabling governed, modular, and
fully automated provisioning of AWS EKS environments.

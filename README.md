# 🚀 Enterprise Infrastructure Automation

```{=html}
<p align="center">
```
`<img src="https://img.shields.io/badge/Terraform-v1.14-623CE4?style=for-the-badge&logo=terraform&logoColor=white"/>`{=html}
`<img src="https://img.shields.io/badge/Jenkins-Pipeline-D24939?style=for-the-badge&logo=jenkins&logoColor=white"/>`{=html}
`<img src="https://img.shields.io/badge/AWS-EKS%20%7C%20VPC-FF9900?style=for-the-badge&logo=amazonaws&logoColor=white"/>`{=html}
`<img src="https://img.shields.io/badge/Infrastructure-as--Code-Enterprise-blue?style=for-the-badge"/>`{=html}
```{=html}
</p>
```

------------------------------------------------------------------------

## 📌 Project Overview

Enterprise-grade Infrastructure Automation pipeline using **Terraform +
Jenkins** to provision and manage AWS infrastructure.

This project demonstrates:

-   Modular Terraform architecture
-   Secure AWS credential injection via Jenkins
-   Automated `init → validate → plan`
-   Manual approval gates
-   Controlled `apply / destroy`
-   Full infrastructure lifecycle automation

------------------------------------------------------------------------

## 🏗 Architecture Overview

**Layers:**

1.  **Source Control** -- GitHub repository
2.  **CI/CD Engine** -- Jenkins Declarative Pipeline
3.  **Infrastructure as Code** -- Terraform Modules
4.  **Cloud Platform** -- AWS (VPC, EKS, IAM, Security Groups)
5.  **State & Governance** -- Terraform state management + approval
    workflow

------------------------------------------------------------------------

## 🔄 CI/CD Workflow

### Stage 1 -- Checkout

Jenkins pulls latest Terraform code from GitHub.

### Stage 2 -- Terraform Init

Initializes backend, downloads providers and modules.

### Stage 3 -- Validate

Validates Terraform syntax and configuration.

### Stage 4 -- Plan

Generates execution plan and stores as artifact.

### Stage 5 -- Approval Gate

Manual enterprise approval before infrastructure modification.

### Stage 6 -- Apply / Destroy

-   Apply approved plan
-   OR controlled infrastructure destroy

------------------------------------------------------------------------

## 🏛 Enterprise Features

-   ✅ Manual Approval Gates\
-   ✅ Secure Credential Handling\
-   ✅ Artifact Archiving\
-   ✅ Controlled Destroy Workflow\
-   ✅ Modular Architecture\
-   ✅ Version-Locked Providers

------------------------------------------------------------------------

## 🔄 Animated CI/CD Pipeline Visualization

```{=html}
<p align="center">
```
`<img src="Terraform-Jenkins-Animated-Pipeline.svg" width="100%"/>`{=html}
```{=html}
</p>
```

------------------------------------------------------------------------

## 🧠 CI/CD Maturity Model

  Level     Description
  --------- ------------------------------------
  Level 1   Manual Infrastructure
  Level 2   Automated Plan
  Level 3   Approval-Based Apply
  Level 4   Full Lifecycle Automation
  Level 5   Enterprise Governance & Compliance

------------------------------------------------------------------------

## 👨‍💻 Author

**Avik Banerjee**\
Cloud \| DevOps \| Infrastructure Automation Engineer

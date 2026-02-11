# 🚀 Enterprise Infrastructure Automation

## Terraform + Jenkins CI/CD Pipeline on AWS

```{=html}
<p align="center">
```
`<img src="https://img.shields.io/badge/Terraform-v1.14+-623CE4?style=for-the-badge&logo=terraform&logoColor=white"/>`{=html}
`<img src="https://img.shields.io/badge/Jenkins-Pipeline-D24939?style=for-the-badge&logo=jenkins&logoColor=white"/>`{=html}
`<img src="https://img.shields.io/badge/AWS-EKS%20%7C%20VPC-FF9900?style=for-the-badge&logo=amazonaws&logoColor=white"/>`{=html}
`<img src="https://img.shields.io/badge/Infrastructure-as--Code-Enterprise-blue?style=for-the-badge"/>`{=html}

```{=html}
</p>
```

------------------------------------------------------------------------

# 📌 Project Overview

This project demonstrates a **production-grade Infrastructure Automation
pipeline** using:

-   Terraform for Infrastructure as Code\
-   Jenkins Declarative Pipeline for CI/CD orchestration\
-   AWS as the cloud provider\
-   EKS + VPC + IAM + Security Groups + NAT Gateway provisioning\
-   Manual approval gates & controlled apply/destroy flows

------------------------------------------------------------------------

# 🏗️ Architecture Overview

## 🔷 High-Level Flow

Developer → GitHub → Jenkins → Terraform → AWS (VPC, IAM, EKS, Security)

------------------------------------------------------------------------

# 🔁 End-to-End Workflow

1.  Developer pushes Terraform code to GitHub\
2.  Jenkins pulls repository\
3.  Terraform initializes providers & modules\
4.  Terraform validates configuration\
5.  Terraform generates execution plan\
6.  Manual approval (if required)\
7.  Apply or Destroy executed\
8.  Status archived & reported

------------------------------------------------------------------------

# ⚙️ Jenkins Pipeline

``` groovy
pipeline {

    agent any

    parameters {
        choice(name: 'action', choices: ['apply', 'destroy'], description: 'Select Terraform action')
        booleanParam(name: 'autoApprove', defaultValue: false, description: 'Skip manual approval?')
    }

    environment {
        AWS_ACCESS_KEY_ID     = credentials('AWS_ACCESS_KEY_ID')
        AWS_SECRET_ACCESS_KEY = credentials('AWS_SECRET_ACCESS_KEY')
    }

    options {
        timestamps()
        buildDiscarder(logRotator(numToKeepStr: '10'))
    }

    stages {

        stage('Checkout') {
            steps {
                cleanWs()
                checkout scm
            }
        }

        stage('Terraform Init') {
            steps {
                sh 'terraform init -input=false'
            }
        }

        stage('Terraform Validate') {
            steps {
                sh 'terraform validate'
            }
        }

        stage('Terraform Plan') {
            when {
                expression { params.action == 'apply' }
            }
            steps {
                sh 'terraform plan -out=tfplan'
                sh 'terraform show -no-color tfplan > tfplan.txt'
            }
        }

        stage('Approval') {
            when {
                allOf {
                    expression { params.action == 'apply' }
                    expression { !params.autoApprove }
                }
            }
            steps {
                script {
                    def plan = readFile 'tfplan.txt'
                    input message: "Approve Terraform Plan?",
                          parameters: [text(name: 'Plan', defaultValue: plan)]
                }
            }
        }

        stage('Apply / Destroy') {
            steps {
                script {
                    if (params.action == 'apply') {
                        sh 'terraform apply -input=false tfplan'
                    } else if (params.action == 'destroy') {
                        sh 'terraform destroy --auto-approve'
                    } else {
                        error "Invalid action selected."
                    }
                }
            }
        }
    }

    post {
        success {
            echo "✅ Infrastructure operation completed successfully."
        }
        failure {
            echo "❌ Terraform deployment failed."
        }
    }
}
```

------------------------------------------------------------------------

# ☁️ AWS Infrastructure Provisioned

-   VPC\
-   Public & Private Subnets\
-   NAT Gateway\
-   IAM Roles & Policies\
-   Security Groups\
-   KMS Encryption\
-   EKS Cluster

------------------------------------------------------------------------

# 🔐 Security Best Practices

-   Credentials stored in Jenkins\
-   No secrets in GitHub\
-   Manual approval gate\
-   Controlled destroy capability\
-   Terraform state locking\
-   Provider version constraints

------------------------------------------------------------------------

# 📊 CI/CD Maturity Alignment

✔ Infrastructure as Code\
✔ Automated Plan\
✔ Manual Governance Gate\
✔ Automated Apply\
✔ Controlled Destroy\
✔ Modular Architecture

------------------------------------------------------------------------

# 🚀 Key Achievements

-   Designed enterprise Terraform pipeline\
-   Provisioned AWS EKS environment\
-   Implemented approval governance\
-   Automated full infrastructure lifecycle

------------------------------------------------------------------------

# 👨‍💻 Author

Avik Banerjee\
Cloud \| DevOps \| Infrastructure Automation Engineer

------------------------------------------------------------------------

# 🔄 Animated CI/CD Pipeline Visualization

Below is the fully animated Terraform + Jenkins pipeline diagram:

![Animated Terraform Jenkins
Pipeline](Terraform-Jenkins-Animated-Pipeline.svg)

> ⚙️ This SVG includes animated flow arrows and enterprise workflow
> visualization.
>
> Recommended: Keep the SVG file in the same repository root for proper
> rendering on GitHub.

------------------------------------------------------------------------

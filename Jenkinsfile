pipeline {

    agent any

    options {
        timestamps()
        disableConcurrentBuilds()
        buildDiscarder(logRotator(numToKeepStr: '10'))
    }

    parameters {
        booleanParam(
            name: 'autoApprove',
            defaultValue: false,
            description: 'Automatically run terraform apply?'
        )
    }

    environment {
        AWS_ACCESS_KEY_ID     = credentials('AWS_ACCESS_KEY_ID')
        AWS_SECRET_ACCESS_KEY = credentials('AWS_SECRET_ACCESS_KEY')
        AWS_DEFAULT_REGION    = 'us-east-1'
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
                sh '''
                    terraform --version
                    terraform init -input=false
                '''
            }
        }

        stage('Terraform Validate') {
            steps {
                sh 'terraform validate'
            }
        }

        stage('Terraform Plan') {
            steps {
                sh '''
                    terraform plan -out=tfplan
                    terraform show -no-color tfplan > tfplan.txt
                '''
            }
        }

        stage('Approval') {
            when {
                expression { return !params.autoApprove }
            }
            steps {
                script {
                    def plan = readFile('tfplan.txt')
                    input message: "Approve Terraform Apply?",
                          parameters: [
                              text(name: 'Terraform Plan',
                                   defaultValue: plan,
                                   description: 'Review the plan before applying')
                          ]
                }
            }
        }

        stage('Terraform Apply') {
            steps {
                sh 'terraform apply -input=false tfplan'
            }
        }

    }

    post {
        always {
            archiveArtifacts artifacts: 'tfplan.txt', fingerprint: true
        }
        success {
            echo "✅ Infrastructure deployed successfully!"
        }
        failure {
            echo "❌ Terraform deployment failed!"
        }
    }
}

pipeline {

    agent any

    options {
        timestamps()
        disableConcurrentBuilds()
    }

    parameters {
        choice(
            name: 'action',
            choices: ['apply', 'destroy'],
            description: 'Choose Terraform action'
        )
        booleanParam(
            name: 'autoApprove',
            defaultValue: false,
            description: 'Skip manual approval?'
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
                dir('terraform') {
                    sh '''
                        terraform --version
                        terraform init -input=false
                    '''
                }
            }
        }

        stage('Terraform Validate') {
            steps {
                dir('terraform') {
                    sh 'terraform validate'
                }
            }
        }

        stage('Terraform Plan') {
            when {
                expression { params.action == 'apply' }
            }
            steps {
                dir('terraform') {
                    sh '''
                        terraform plan -out=tfplan
                        terraform show -no-color tfplan > tfplan.txt
                    '''
                }
            }
        }

        stage('Apply / Destroy') {
            steps {
                dir('terraform') {
                    script {

                        if (params.action == 'apply') {

                            if (!params.autoApprove) {
                                def plan = readFile 'tfplan.txt'
                                timeout(time: 10, unit: 'MINUTES') {
                                    input(
                                        message: "Do you want to APPLY this Terraform plan?",
                                        ok: "Apply",
                                        parameters: [
                                            text(
                                                name: 'Plan',
                                                description: 'Review the plan before approving',
                                                defaultValue: plan
                                            )
                                        ]
                                    )
                                }
                            }

                            sh 'terraform apply -input=false tfplan'

                        } else if (params.action == 'destroy') {

                            if (!params.autoApprove) {
                                timeout(time: 10, unit: 'MINUTES') {
                                    input(
                                        message: "⚠️ Are you sure you want to DESTROY all infrastructure?",
                                        ok: "Destroy"
                                    )
                                }
                            }

                            sh 'terraform destroy -auto-approve'

                        } else {
                            error "Invalid action selected. Choose apply or destroy."
                        }
                    }
                }
            }
        }
    }

    post {

        success {
            echo "✅ Terraform ${params.action} completed successfully!"
        }

        failure {
            echo "❌ Terraform ${params.action} failed!"
        }

        always {
            archiveArtifacts artifacts: 'terraform/*.txt', allowEmptyArchive: true
        }
    }
}

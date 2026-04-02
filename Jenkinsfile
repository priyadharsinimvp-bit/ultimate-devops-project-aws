pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git 'https://github.com/priyadharsinimvp-bit/ultimate-devops-project-aws.git'
            }
        }

        stage('Verify Project') {
            steps {
                echo "This is a Terraform/DevOps project. No Maven build needed."
            }
        }

        stage('Terraform Init') {
            steps {
                dir('section-1') {
                    bat 'terraform init'
                }
            }
        }

        stage('Terraform Plan') {
            steps {
                dir('section-1') {
                    bat 'terraform plan'
                }
            }
        }

        stage('Deploy') {
            steps {
                echo "Deployment step placeholder"
            }
        }
    }
}
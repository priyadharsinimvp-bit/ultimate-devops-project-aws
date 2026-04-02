pipeline {
    agent any

    options {
        skipDefaultCheckout(true)
    }

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/priyadharsinimvp-bit/ultimate-devops-project-aws.git'
            }
        }

        stage('Build') {
            steps {
                echo 'No build needed'
            }
        }

        stage('Test') {
            steps {
                echo 'No tests'
            }
        }

        stage('SonarQube Analysis') {
            steps {
                echo 'Skipping SonarQube'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploy step'
            }
        }
    }
}
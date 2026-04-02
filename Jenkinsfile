pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/priyadharsinimvp-bit/ultimate-devops-project-aws.git'
            }
        }

        stage('Build') {
            steps {
                dir('section-1') {
                    bat 'echo Building project...'
                    bat 'timeout /t 5'
                }
            }
        }

        stage('Test') {
            steps {
                dir('section-1') {
                    bat 'echo Running tests...'
                    bat 'timeout /t 5'
                }
            }
        }

        stage('SonarQube Analysis') {
            steps {
                bat 'echo Running SonarQube...'
                bat 'timeout /t 5'
            }
        }

        stage('Package') {
            steps {
                bat 'echo Packaging...'
                bat 'timeout /t 5'
            }
        }

        stage('Deploy') {
            steps {
                bat 'echo Deploying...'
                bat 'timeout /t 5'
            }
        }
    }
}
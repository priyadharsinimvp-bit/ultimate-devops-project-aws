pipeline {
    agent any

    tools {
        maven 'Maven'
    }

    stages {

        stage('Checkout') {
            steps {
                git 'https://github.com/priyadharsinimvp-bit/ultimate-devops-project-aws.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean compile'
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }

        stage('SonarQube Analysis') {
            steps {
                withSonarQubeEnv('sonarqube-server') {
                    sh '''
                    mvn sonar:sonar \
                    -Dsonar.projectKey=ultimate-devops-project \
                    -Dsonar.host.url=http://localhost:9000
                    '''
                }
            }
        }

        stage('Package') {
            steps {
                sh 'mvn package'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploy step (Nginx next)'
            }
        }
    }
}
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
                bat 'mvn clean compile'
            }
        }
 
        stage('Test') {
            steps {
                bat 'mvn test'
            }
        }
 
        stage('SonarQube Analysis') {
            steps {
                withSonarQubeEnv('sonarqube-server') {
                    bat """
                    mvn sonar:sonar ^
                    -Dsonar.projectKey=ultimate-devops ^
                    -Dsonar.host.url=http://localhost:9000
                    """
                }
            }
        }
 
        stage('Package') {
            steps {
                bat 'mvn package'
            }
        }
 
        stage('Deploy') {
            steps {
                echo 'Deploy step'
            }
        }
    }
}
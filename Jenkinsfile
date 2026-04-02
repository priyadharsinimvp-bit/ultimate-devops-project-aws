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
                dir('section-1') {
                    bat 'mvn clean compile'
                }
            }
        }

        stage('Test') {
            steps {
                dir('section-1') {
                    bat 'mvn test'
                }
            }
        }

        stage('SonarQube Analysis') {
            steps {
                dir('section-1') {
                    withSonarQubeEnv('sonarqube-server') {
                        bat """
                        mvn sonar:sonar ^
                        -Dsonar.projectKey=ultimate-devops ^
                        -Dsonar.host.url=http://localhost:9000
                        """
                    }
                }
            }
        }

        stage('Package') {
            steps {
                dir('section-1') {
                    bat 'mvn package'
                }
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploy step'
            }
        }
    }
}
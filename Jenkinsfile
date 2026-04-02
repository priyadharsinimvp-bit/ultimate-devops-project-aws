pipeline {
    agent any

    tools {
        maven 'Maven'
    }

    stages {

        stage('Build') {
            steps {
                dir('section-1') {   // 👈 CHANGE THIS
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
                        bat '''
                        mvn sonar:sonar ^
                        -Dsonar.projectKey=ultimate-devops ^
                        -Dsonar.host.url=http://localhost:9000
                        '''
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
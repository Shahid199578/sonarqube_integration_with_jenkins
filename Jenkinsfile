pipeline {
    agent any

    tools {
        maven 'Maven-Tool'
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'master', url: 'https://github.com/Shahid199578/sonarqube_integration_with_jenkins.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('SonarQube Analysis') {
            steps {
                withSonarQubeEnv('sonar-jenkins') {
                    sh 'mvn sonar:sonar \
                      -Dsonar.projectKey=jenkins \
                      -Dsonar.host.url=http://54.197.177.182:9000 \
                      -Dsonar.login=14da92f285c610f98780db44e07c81f6883405d7'
                }
            }
        }
    }

    post {
        always {
            deleteDir()
        }
    }
}

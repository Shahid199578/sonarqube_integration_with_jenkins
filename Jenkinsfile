pipeline {
    agent any

    tools {
        maven 'Maven-Tool'
    }

    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/Shahid199578/sonarqube_integration_with_jenkins.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('SonarQube Analysis') {
            steps {
                sh 'mvn sonar:sonar \
                    -Dsonar.projectKey=Jeninks \
                    -Dsonar.host.url=http://172.31.88.235:9000 \
                    -Dsonar.login=14da92f285c610f98780db44e07c81f6883405d7'
            }
        }
    }

    post {
        always {
            deleteDir()
        }
    }
}

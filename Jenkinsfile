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

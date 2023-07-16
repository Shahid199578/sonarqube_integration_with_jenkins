pipeline {
    agent any
    
    environment {
        SONARQUBE_HOME = tool 'sonar'
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
                withSonarQubeEnv('SonarQube Server') {
                    sh "${SONARQUBE_HOME}/bin/sonar-scanner"
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

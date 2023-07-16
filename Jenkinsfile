pipeline {
    agent any
    
    environment {
        SONARQUBE_HOME = tool 'sonarscanner'
    }

    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/logicopslab/java-web-app.git'
            }
        }
        
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }
        
        stage('SonarQube Analysis') {
            steps {
                withSonarQubeEnv(credentialsId: 'sonar-jenkins') {
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

pipeline {
    agent any
    environment {
        CI = 'true'
    }
    stages {
        stage('Prepare Environment') {
            steps {
                script {
                    // Ensure npm is available by installing Node.js
                    sh 'sudo apt update'
                    sh 'sudo apt install -y nodejs npm'
                }
            }
        }
        stage('Build') {
            steps {
                sh 'npm install'
            }
        }
        stage('Test') {
            steps {
                sh './jenkins/scripts/test.sh'
            }
        }
    }
}

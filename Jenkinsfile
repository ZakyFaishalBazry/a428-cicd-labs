pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                script {
                    docker.image('node:18-buster-slim').inside('-p 3000:3000') {
                        sh 'npm install'
                    }
                }
            }
        }
        
        stage('Test') {
            steps {
                script {
                    docker.image('node:18-buster-slim').inside('-p 3000:3000') {
                        sh './jenkins/scripts/test.sh'
                    }
                }
            }
        }
    }
}
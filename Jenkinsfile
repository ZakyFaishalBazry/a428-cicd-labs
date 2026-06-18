pipeline {
    agent any // Ubah bagian atas menjadi any
    stages {
        stage('Build') { 
            agent {
                docker {
                    image 'node:18-buster-slim' 
                    args '-p 3000:3000' 
                }
            }
            steps {
                sh 'npm install'
            }
        }
        
        stage('Test') {
            agent {
                docker {
                    image 'node:18-buster-slim' 
                    args '-p 3000:3000' 
                }
            }
            steps {
                sh './jenkins/scripts/test.sh'
            }
        }
    }
}
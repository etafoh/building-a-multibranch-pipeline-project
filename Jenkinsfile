pipeline {
    agent {
        docker {
            image 'node:6-alpine'
            args '-p 3000:3000 -p 5000:5000' 
        }
    }
    environment {
        CI = 'true'
    }
    stages {
        stage('Build application') {
            steps {
                sh 'npm install'
            }
        }
        stage('Test application') {
            steps {
                sh './jenkins/scripts/test.sh'
            }
        }
    }
}

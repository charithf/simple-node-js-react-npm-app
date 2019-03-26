pipeline {
    agent {
        docker {
            image 'node:6-alpine' 
            args '-p 3000:3000' 
        }
    }
    environment {
        CI = 'true'
    }
    stages {
        stage('Build System 1133') { 
            steps {
                sh 'npm install' 
            }
        }
        stage('Test Application 21') {
            steps {
                sh './jenkins/scripts/test.sh'
            }
        }
	stage('Deliver Product 31') {
            steps {
                sh './jenkins/scripts/deliver.sh'
                input message: 'Finished using the web site? (Click "Proceed" to continue)'
                sh './jenkins/scripts/kill.sh'
            }
        }
    }
}
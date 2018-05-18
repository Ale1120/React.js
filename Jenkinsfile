pipeline {
    agent {
        docker {
            image 'node'
            args '-p 9000:9000'
        }
    }
    environment {
        CI = 'true'
    }
    stages {
        stage('Build') {
            steps {
                sh 'npm install'
            }
        }
        stage('Deliver') {
            steps {
                sh 'npm run build:dev'
                input message: 'Finished using the web site? (Click "Proceed" to continue)'
            }
        }
    }
}

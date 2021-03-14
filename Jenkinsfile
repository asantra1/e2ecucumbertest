pipeline {
    environment {
        PATH = "$PATH:/usr/local/bin"
    }
    agent {
        docker { image 'node:14-alpine' }
    }
    stages {
        stage('Test') {
            steps {
                sh 'node --version'
            }
        }
    }
}

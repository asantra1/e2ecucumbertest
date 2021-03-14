pipeline {
    environment {
        PATH = "$PATH:/usr/local/bin"
    }
    agent any
    stages {
        stage('Test') {
            steps {
                checkout scm
                sh '''
                  docker-compose up cucumbertests 
                '''
            }
        }
    }
}

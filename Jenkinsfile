pipeline {
    agent {
        docker { image 'jpetazzo/dind' }
    }
    stages {
        stage('Test') {
            steps {
                sh 'docker info'
            }
        }
    }
}

pipeline {
  agent {
    kubernetes {
      yaml """\
        apiVersion: v1
        kind: Pod
        metadata:
          labels:
            k8-name: cucumber
        spec:
          containers:
          - name: dind
            image: jpetazzo/dind:latest
            command:
            - cat
            tty: true
        """.stripIndent()
    }
  }
  stages {
    stage('Docker Build') {
      steps {
        container('dind') {
          sh '''
             
          '''
        }
      }
    }
  }
}


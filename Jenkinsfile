pipeline {
  agent {
    kubernetes {
      yaml """\
        apiVersion: v1
        kind: Pod
        spec:
          volumes:
          - name: docker-socket
            emptyDir: {}
          containers:
          - name: docker 
            image: docker:19.03.1
            command:
            - sleep
            args:
            - 100d
            volumeMounts:
            - name: docker-socket
              mountPath: /var/run
          - name: docker-daemon
            image: docker:19.03.1-dind
            securityContext:
              privileged: true
            volumeMounts:
            - name: docker-socket
              mountPath: /var/run
                """.stripIndent()
    }
  }
  stages {
    stage('Docker Build') {
      steps {
        container('docker') {
          checkout scm

          sh '''
             docker info
          '''
        }
      }
    }
  }
}

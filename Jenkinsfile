pipeline {
    agent {    
        kubernetes {
            label 'mc-client'
            defaultContainer 'jnlp'
            yaml """
            apiVersion: v1
            kind: Pod
            metadata:
              name: helm
            spec:
              containers:
                - name: mc
                image: minio/mc
                command:
                - cat
                tty: true
            """
        }
    }
    stages {
      stage('mc client test') {
        steps {
          container('mc') {
            sh 'mc admin --help'
          }
        }
      }
    }       
}

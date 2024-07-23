pipeline {
    agent {    
        kubernetes {
            label 'mc-client'
            defaultContainer 'jnlp'
            yaml """
           apiVersion: v1
           kind: Pod
           metadata:
             name: mc
           spec:
             containers:
             - command:
               - cat
               tty: true
               securityContext:
                 privileged: true
               image: minio/mc
               name: mc
               volumeMounts:
                 - name: varlibcontainers
                   mountPath: /var/lib/containers
             volumes:
               - name varlibcontainers
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

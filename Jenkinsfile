pipeline {
     agent {
    kubernetes {
      yaml '''
apiVersion: v1
kind: Pod
metadata:
  name: mc
spec:
  containers:
  - name: mc
    image: minio/mc
    command:
    - cat
    tty: true
    securityContext:
      privileged: true
    volumeMounts:
      - name: varlibcontainers
        mountPath: /var/lib/containers
  volumes:
    - name: varlibcontainers
'''   
    }
  }
    stages {
      stage('mc client test') {
        steps {
          container('mc') {
            sh 'mc cp index.yaml  http://minio.kube.local/helm-repository --help'
          }
        }
      }
    }       
}

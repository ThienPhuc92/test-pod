pipeline {
  agent any
  environment {
    IMAGE_REPO = 'nexus-pod'
    NAME = 'wordpress-pod'
  }
  stages {
    stage('Build') {
      steps {
        sh 'docker build -t pod-repositories/${NAME}:latest .'
        sh 'docker push 172.20.0.6:5000/repository/pod-repositories/${NAME}:latest'
        sh 'docker pull 172.20.0.6:5000/repository/pod-repositories/${NAME}:latest'
        sh 'docker stop wordpress-pod'
        sh 'docker run --name wordpress-pod -p 8097:80 -d pod-repositories/${NAME}:latest'
      }
    }
  }
}

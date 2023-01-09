pipeline {
  agent any
  environment {
    IMAGE_REPO = 'nexus-pod' 
    NAME = 'wordpress-pod'
  }
  stages {
    stage('Build') {
      steps {
        sh 'docker build -t 172.24.0.5:5000/repository/pod-repositories/${NAME}:latest .'
        sh 'docker push 172.24.0.5:5000/repository/pod-repositories/${NAME}:latest'
      }
    }
  }
}

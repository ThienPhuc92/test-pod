pipeline {
  agent any
  environment {
    IMAGE_REPO = 'nexus-pod' 
    NAME = 'wordpress-pod'
  }
  stages {
    stage('Build') {
      steps {
        sh 'docker build -t ${NAME}:latest .'
        sh 'docker push https://repo.thienphuc92dn.com/repository/pod-repositories/'
      }
    }
  }
}

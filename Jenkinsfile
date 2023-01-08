pipeline {
  agent any
  environment {
    IMAGE_REPO = 'nexus-pod' 
    NAME = 'wordpress-pod'
  }
  stages {
    stage('Build') {
      steps {
        sh 'docker build -t repo.thienphuc92dn.com/repository/pod-repositories:5443/${NAME}:latest .'
        sh 'docker push repo.thienphuc92dn.com/repository/pod-repositories:5443/${NAME}:latest'
      }
    }
  }
}

pipeline {
  agent any
  environment {
    IMAGE_REPO = 'nexus-pod' 
    NAME = 'wordpress-pod'
  }
  stages {
    stage('Build') {
      steps {
        sh 'docker build ${NAME} -t ${NAME}:latest -t ${IMAGE_REPO}/${NAME}:${env.BUILD_ID} .'
      }
    }
  }
}

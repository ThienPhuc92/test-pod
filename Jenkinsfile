pipeline {
  agent any
  environment {
    DOCKER_FILE_PATH = '~/project/wordpress-pod'
    IMAGE_REPO = 'nexus-pod'
    NAME = 'wordpress-pod'
    VERSION = '${env.BUILD_ID}-${env.GIT_COMMIT}'
    IMAGE = '${NAME}:${VERSION}'
  }
  stages {
    stage('Checkout git') {
      steps {
        checkout scm
      }
    }
    stage('Build') {
      steps {
        sh 'docker build ${NAME} -f ${DOCKER_FILE_PATH} -t ${NAME}:latest -t ${IMAGE_REPO}/${NAME}:${VERSION} .'
      }
    }
  }
}

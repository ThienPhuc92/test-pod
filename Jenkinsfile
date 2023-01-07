pipeline {
  agent any
  environment {
    IMAGE_REPO = 'nexus-pod'
    NAME = 'wordpress-pod'
    VERSION = '${env.BUILD_ID}-${env.GIT_COMMIT}'
    IMAGE = '${NAME}:${VERSION}'
  }
  stages {
    stage('Build') {
      steps {
        echo "Name: ${NAME}"
        echo "Version: ${VERSION}"
        echo "${env.BUILD_ID}-${env.GIT_COMMIT}"
        echo """${env.BUILD_ID}-${env.GIT_COMMIT}"""
        sh 'docker build ${NAME} -t ${NAME}:latest -t ${IMAGE_REPO}/${NAME}:${VERSION} .'
      }
    }
  }
}

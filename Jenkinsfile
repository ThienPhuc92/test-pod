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
        echo "Version: ${VERSION}"
        sh 'docker build ${NAME} -t ${NAME}:latest -t ${IMAGE_REPO}/${NAME}:${VERSION} .'
      }
    }
  }
}

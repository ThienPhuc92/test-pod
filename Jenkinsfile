pipeline {
  agent any
  environment {
    IMAGE_REPO = 'nexus-pod'
    NAME = 'wordpress-pod'
    VERSION = '${BUILD_ID}-${GIT_COMMIT}'
    IMAGE = '${NAME}:${VERSION}'
  }
  stages {
    stage("List env vars"){
			steps{
				sh "printenv | sort"
			}
		}
    stage('Build') {
      steps {
        echo "Name: ${NAME}"
        echo "Version: ${VERSION}"
        sh 'docker build ${NAME} -t ${NAME}:latest -t ${IMAGE_REPO}/${NAME}:${VERSION} .'
      }
    }
  }
}

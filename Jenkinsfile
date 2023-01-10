pipeline {
  agent any
  environment {
    IMAGE_REPO = 'nexus-pod'
    NAME = 'wordpress-pod'
  }
  stages {
    stage('Build') {
      steps {
        sh 'docker build . -f docker/Dockerfile -t pod-repositories/${NAME}:latest'
        sh 'docker image tag pod-repositories/${NAME}:latest pod-repositories/${NAME}:${GIT_COMMIT}'
        sh 'docker push 172.20.0.6:5000/repository/pod-repositories/${NAME}:latest'
        sh 'docker pull 172.20.0.6:5000/repository/pod-repositories/${NAME}:latest'
        sh 'docker rm -f wordpress-pod'
        sh 'docker compose -f docker/docker-compose.yml up'
      }
    }
  }
}

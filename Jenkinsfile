pipeline {
  agent any
  environment {
    DOCKERHUB_CREDENTIALS = credentials('padma-dockerhub')
  }
  stages {
    stage('Login') {
      steps {
        sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
      }
    }
    stage('Pull') {
      steps {
        sh 'docker pull dhub2000/padma-alpine:${BUILD_NUMBER-1}'
      }
    }
  }
  post {
    always {
      sh 'docker logout'
    }
  }
}

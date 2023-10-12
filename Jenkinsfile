pipeline {
  agent any
  environment {
    DOCKERHUB_CREDENTIALS = credentials('padma-dockerhub')
  }
  stages {
    stage('Build') {
      steps {
        sh 'docker build -t dhub2000/padma-alpine:latest .'
      }
    }
    stage('Login') {
      steps {
        sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
      }
    }
    stage('Push') {
      steps {
        sh ''
      }
    }
  }
  post {
    always {
      sh 'docker logout'
    }
  }
}

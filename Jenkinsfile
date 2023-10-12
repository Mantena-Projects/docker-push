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
        sh ''
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

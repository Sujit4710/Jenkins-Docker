pipeline {
  agent any
  options {
    buildDiscarder(logRotator(numToKeepStr: '5'))
  }
  environment {
    DOCKERHUB_CREDENTIALS = credentials('dockerhub')
  }
  stages {
    stage('Build') {
      steps {
        sh 'docker build -t sujit44/jenkins-docker-hub .'
      }
    }
    stage('Login') {
      steps {
        sh 'echo $dockerhub | docker login -u $sujit44 --Sujit@4710'
      }
    }
    stage('Push') {
      steps {
        sh 'docker push sujit44/jenkins-docker-hub'
      }
    }
  }
  post {
    always {
      sh 'docker logout'
    }
  }
}
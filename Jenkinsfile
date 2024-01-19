pipeline {
  agent {
    label 'docker'
  }
  stages {
    stage('Docker Build') {
      steps {
        sh '''
        docker build -t demo-docker .
        docker tag demo-docker:latest jenkins/pg-docker/demo-docker:latest
        '''
      }
    }
    stage('Test') {
      steps {
        sh '''
        docker images -a
        '''
      }
    }
  }
}

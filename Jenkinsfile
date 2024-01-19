pipeline {
  agent any
  stages {
    stage('Git Clone Repo') {
      steps {
        scripts {
          git url: 'https://github.com/petkovp/multiBranch.git'
        }
      }
    }
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

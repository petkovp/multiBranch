pipeline {
  agent {
    docker { image 'jenkins/jnlp-agent-docker' args '-u root' }
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

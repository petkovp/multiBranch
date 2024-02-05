pipeline {
  agent {
    kubernetes {
      inheritFrom 'aws-pod'
    }
  }
  stages {
    stage('Build') {
      steps {
        container('aws-pod') {
          echo "building"
        }
      }
    }
    stage('AWS S3 List') {
      steps {
        container('aws-pod') {
          sh '''
          aws s3 ls
          '''
        }
      }
    }
  }
  options {
    disableResume()
  }
}

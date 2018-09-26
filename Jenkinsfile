pipeline {
  agent any  
  stages {
    stage('Building the docker image') {
      environment {
        imageTag = 'sampleflask'
      }
      steps {
        sh('docker build -t ${imageTag} .')
      }
    }
  }
}

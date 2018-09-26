pipeline {
  agent none  
  environment {
    imageTag = 'sampleflask'
    stages {
      stage('Building the docker image') {
        steps {
          sh('docker build -t ${imageTag} .')
        }
      }
    }
  }
}

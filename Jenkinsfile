pipeline {
  agent any  
  stages {
    stage('Building the docker image') {
      environment {
        imageTag = 'sampleflask'
      }
      steps {
        sh('sudo docker build -t ${imageTag} .')
        sh("docker push ${imageTag}")
        sh('docker run -d -p 5000:5000 ${imageTag}')
      }
    }
  }
}

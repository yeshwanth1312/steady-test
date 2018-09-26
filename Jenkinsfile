pipeline {
  agent any  
  stages {
    stage('Building the docker image') {
      environment {
        imageTag = 'sampleflask'
      }
      steps {
        sh('sudo docker build -t ${imageTag} .')
    stage('Push image to registry') {
      environment {
        imageTag = 'sampleflask'
      }  
      steps {
        sh("docker push ${imageTag}")
      }
    }
    stage('Deploy Application') {
      environment {
        imageTag = 'sampleflask'
      }
      steps {
        sh('docker run -d -p 5000:5000 ${imageTag}')
      }
      }
    }
    }
  }
}

pipeline {
  agent none  
  environment {
    imageTag = 'sampleflask'
  }
  stages {
    stage('Building the docker image') {
      steps {
        sh("docker build -t ${imageTag} .")
      }
    }
     stage('Push image to registry') {
       steps {
         sh("docker push ${imageTag}")
       }
     }
     stage('Deploy Application') {
       steps {
         sh('docker run -d -p 5000:5000 ${imageTag}')
       }
     }
  }
}

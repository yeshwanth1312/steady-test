pipeline {
  agent any  
  stages {
    stage('Building the docker image') {
      environment {
        imageTag = 'sampleflask'
      }
      options {
        timeout(time:60, unit: 'SECONDS')
      }
      steps {
        sh('sudo docker build -t ${imageTag} .')
        sh('sudo docker push ${imageTag}')
        sh('sudo  docker run -d -p 5000:5000 ${imageTag}')
      }
    }
  }
}

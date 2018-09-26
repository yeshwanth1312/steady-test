pipeline {
  agent any  
  stages {
    stage('Building the docker image') {
      environment {
        imageTag = 'sampleflask:latest'
      }
      options {
        timeout(time:180, unit: 'SECONDS')
      }
      steps {
        withDockerRegistry9[credentialsID: 'cheruku459', url: 'docker.io/my-account']) {
        }
          sh('sudo docker build -t ${imageTag} .')
          sh('sudo docker push ${imageTag}')
          sh('sudo  docker run -d -p 5000:5000 ${imageTag}')
      }
    }
  }
}

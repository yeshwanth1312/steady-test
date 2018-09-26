pipeline {
  agent any  
  environment {
    imageTag = 'sampleflask'
  }
  stages {
    stage('Building the docker image') {
      steps {
        sh('sudo docker build -t ${imageTag} .')
      }
    }
     stage('Push image to registry') {
       steps {
         withDockerRegistry9[credentialsId: "cheruku459", url: "https://hub.docker.com/r/cheruku459/rajasekhar/"]) {
         sh('sudo docker push ${imageTag}')
         }
       }
     }
  }
}

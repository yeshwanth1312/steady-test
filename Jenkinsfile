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
         withCredentials([string(credentialsId: 'docker-pwd', variable: 'dockerhubPasswd')]) {
           sh "docker login -u cheruku459 -p ${dockerhubPasswd}"
         }
         sh('sudo docker push ${imageTag}')
         }
       }
     }
  }
}

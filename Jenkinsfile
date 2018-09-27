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
          sh('sudo docker login -u cheruku459 -p ${dockerhubPasswd}')
        }
        sleep 300
        sh('sudo docker push ${imageTag}')
      }
    }
  }
} 

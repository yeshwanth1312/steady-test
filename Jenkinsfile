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
        sh('sudo docker tag ${imageTag} cheruku459/rajasekhar:${imageTag}')
        sh('sudo docker push cheruku459/rajasekhar:${imageTag}')
      }
    }
    
    stage('Running the container') { 
      steps {
        sh('sudo docker run -p 5000:5000 ${imageTag}')
      }
    }  
  }
} 

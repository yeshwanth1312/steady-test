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
        withCredentials([string(credentialsId: 'docker', variable: 'dockerhubPasswd')]) {
          sh('sudo docker login -u yeshwanthjavvaji -p ${dockerhubPasswd}')
        }
        sh('sudo docker tag ${imageTag} yeshwanthjavvaji/steady:${imageTag}')
        sh('sudo docker push yeshwanthjavvaji/steady:${imageTag}')
      }
    }
    
    stage('Running the container') { 
      steps {
        sh('sudo docker run -d -p 5000:5000 ${imageTag}')
      }
    }  
  }
} 

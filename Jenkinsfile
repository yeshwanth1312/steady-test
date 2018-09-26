pipeline {
  environment {
    registry = "cheruku459/rajasekhar"
    registryCredential = "dockerhub"
  }
  agent any  
  stages {
    stage('Cloning Git') {
      steps {
        git 'https://github.com/yeshwanth1312/steady-test.git'
      }
   }
   stage('Building the docker image') {
      steps{ 
        script {  
          docker.build registry + ":$BUILD_NUMBER"  
        }
      }
    }
  }
}

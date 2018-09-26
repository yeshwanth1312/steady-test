pipeline {
    agent any
    stages {
        stage('Build image') {
            steps {
                echo 'Starting to build docker image'

                script {
                    def customImage = sudo docker.build("my-image:${env.BUILD_ID}")
                    customImage.push()
                }
            }
        }
    }
}

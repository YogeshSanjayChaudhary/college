pipeline {
    agent any

    stages {
        stage('Build Docker Image') {
            steps {
                script {
                 def customImage = docker.build('yogeshchaudhary/college')
                 docker.withRegistry('https://registry.hub.docker.com', 'dockerhub') {
                 customImage.push("${env.BUILD_NUMBER}")
                 }
               }
            }
        }
    }
}

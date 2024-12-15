pipeline {
    agent any

    stages {
        stage('Docker Build') {
            steps {
                echo 'Pushing Docker Image to Docker Hub...'
                withCredentials([usernamePassword(credentialsId: 'my-docker-hub', 
                                               usernameVariable: 'DOCKER_USERNAME', 
                                               passwordVariable: 'DOCKER_PASSWORD')]) {
                    script {
                        sh "docker compose up"
                        // Log in to Docker Hub
                        sh "echo ${DOCKER_PASSWORD} | docker login -u ${DOCKER_USERNAME} --password-stdin"                       
                        // Push the image
                        sh "docker push ${DOCKER_USERNAME}/first-node-docker-compose:jenkins"
                         }
                }
            }
        }
    }
}
pipeline {
    agent any

    stages {
       
        stage('Docker Build') {
            steps {
                echo 'Pushing Docker Image to Docker Hub...'
                    script {
                        withCredentials([usernamePassword(credentialsId: 'my-docker-hub', 
                                                  usernameVariable: 'DOCKER_USERNAME', 
                                                  passwordVariable: 'DOCKER_PASSWORD')]) {
                            sh "echo $DOCKER_PASSWORD | docker login -u $DOCKER_USERNAME --password-stdin"
                            sh "docker-compose up"                   
                            // Push the image
                            sh "docker push ahmedsakr98/first-node-docker-compose:jenkins"
                        }
                    }
            }
        }
    }
}
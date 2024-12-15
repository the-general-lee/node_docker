pipeline {
    agent any

    stages {
        stage('Docker Build') {
            steps {
                echo 'Pushing Docker Image to Docker Hub...'
                    script {
                        sh "docker compose up"                   
                        // Push the image
                        sh "docker push ahmedsakr98/first-node-docker-compose:jenkins"
                         }
            }
        }
    }
}
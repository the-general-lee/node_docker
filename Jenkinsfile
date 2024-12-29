pipeline {
    agent {label nodejs}

    stages {
        stage('Test Cases') {
            steps {
                echo 'Running npm tests...'
                script {
                    // Run npm test
                    sh "npm install"
                    sh "npm test"
                }
            }
        }

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
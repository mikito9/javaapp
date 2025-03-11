// Jenkinsfile
pipeline {
    agent any

    environment {
        DOCKER_IMAGE = "myapp-image"  // Docker image name
        DOCKER_CONTAINER = "myapp-container"  // Docker container name
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/mikito9/javaapp.git'  // Replace with your repo URL
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'  // Build the Java application (adjust for your build tool)
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    docker.build("${DOCKER_IMAGE}")
                }
            }
        }

        stage('Run Docker Container') {
            steps {
                script {
                    // Stop and remove existing container (if any)
                    sh "docker stop ${DOCKER_CONTAINER} || true"
                    sh "docker rm ${DOCKER_CONTAINER} || true"

                    // Run the new container
                    sh "docker run -d --name ${DOCKER_CONTAINER} -p 8080:8080 ${DOCKER_IMAGE}"
                }
            }
        }
    }

    post {
        success {
            echo 'Deployment successful!'
        }
        failure {
            echo 'Deployment failed!'
        }
    }
}

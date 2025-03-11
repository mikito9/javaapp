pipeline {
    agent any // Correct usage of 'agent any'

    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/mikito9/javaapp.git'
            }
        }

        stage('Build') {
            steps {
                echo 'Building the application...'
                // Add build steps here (e.g., Maven, Gradle, etc.)
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                // Add test steps here
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying the application...'
                // Add deployment steps here
            }
        }
    }

    post {
        success {
            echo 'Pipeline succeeded!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}

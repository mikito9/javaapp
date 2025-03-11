pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', 
                    url: 'https://github.com/mikito9/javaapp.git', 
                    credentialsId: 'mikito9'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'  // Adjust for your build tool
            }
        }

        stage('Deploy') {
            steps {
                sh 'echo "Deploying application..."'
            }
        }
    }
}

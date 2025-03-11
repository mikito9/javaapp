pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', 
                    url: 'https://github.com/mikito9/javaapp.git', 
                    credentialsId: 'mikito9'  // Replace with your credentials ID
            }
        }
        // Other stages...
    }
}

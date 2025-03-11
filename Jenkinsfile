pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/mikito9/javaapp.git'
            }
        }

        stage('Unzip HTML') {
            steps {
                script {
                    // Check if javaapp.zip exists
                    if (fileExists('javaapp.zip')) {
                        sh 'unzip -o javaapp.zip -d ./'
                    } else {
                        error 'javaapp.zip not found!'
                    }
                }
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t javaapp .'
            }
        }

        stage('Run Docker Container') {
            steps {
                sh 'docker run -d -p 8080:8080 javaapp'
            }
        }
    }

    post {
        failure {
            echo 'Pipeline failed! Check the logs for more details.'
        }
        success {
            echo 'Pipeline succeeded!'
        }
    }
}pipeline {
    agent any
    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/mikito9/javaapp.git'
            }
        }
        stage('Unzip HTML') {
            steps {
                sh 'unzip -o javaapp.zip -d ./'
            }
        }
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t my-html-site .'
            }
        }
        stage('Run Docker Container') {
            steps {
                sh 'docker run -d -p 8080:80 my-html-site'
            }
        }
    }
}


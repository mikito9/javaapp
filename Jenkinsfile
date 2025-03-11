pipeline {
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


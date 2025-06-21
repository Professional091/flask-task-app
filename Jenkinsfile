pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/Professional091/flask-task-app.git'
            }
        }
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t flask-task-app .'
            }
        }
        stage('Run Docker Container') {
            steps {
                sh 'docker run -d -p 5000:5000 --name flask-app flask-task-app'
            }
        }
    }
}

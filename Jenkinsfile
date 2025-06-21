pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Professional091/flask-task-app.git'
            }
        }
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t flask-task-app .'
            }
        }
        stage('Run Docker Container') {
            steps {
                // Stop and remove existing container (optional)
                sh 'docker rm -f flask-app || true'
                // Run the new container
                sh 'docker run -d -p 5000:5000 --name flask-app flask-task-app'
            }
        }
    }
}

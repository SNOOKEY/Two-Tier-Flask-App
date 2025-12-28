https://github.com/SNOOKEY/Two-Tier-Flask-App.git
pipeline {
    agent any
    stages {
        stage('Clone Code') {
            stage('Clone Code') {
    steps {
        git branch: 'main', url: 'https://github.com/SNOOKEY/Two-Tier-Flask-App.git'
    }
}
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t flask-app:latest .'
            }
        }
        stage('Deploy with Docker Compose') {
            steps {
                // Stop existing containers if they are running
                sh 'docker compose down || true'
                // Start the application, rebuilding the flask image
                sh 'docker compose up -d --build'
            }
        }
    }
}
}

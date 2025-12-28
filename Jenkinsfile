pipeline {
    agent any

    stages {
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
                // Stop existing containers if running
                sh 'docker compose down || true'
                // Start the application
                sh 'docker compose up -d --build'
            }
        }
    }
}

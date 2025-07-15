pipeline {
    agent any
    stages {
        stage('Clone Code') {
            steps {
                git 'https://github.com/<your-username>/flask-cicd.git'
            }
        }
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t flask-cicd-app .'
            }
        }
        stage('Run Docker Container') {
            steps {
                sh 'docker rm -f flask-cicd || true'
                sh 'docker run -d -p 5000:5000 --name flask-cicd flask-cicd-app'
            }
        }
    }
}

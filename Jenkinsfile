pipeline {
    agent any
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t flask-cicd-app .'
            }
        }
        stage('Run Container') {
            steps {
                sh 'docker rm -f flask-cicd || true'
                sh 'docker run -d -p 5000:5000 --name flask-cicd flask-cicd-app'
            }
        }
    }
}


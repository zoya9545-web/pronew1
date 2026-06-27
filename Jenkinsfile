pipeline {
    agent any

    stages {

        stage('Checkout Code') {
            steps {
                git branch: 'main',
                url: 'https://github.com/zoya9545-web/pronew1.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t pronew1:latest .'
            }
        }

        stage('Run Container') {
            steps {
                sh '''
                docker stop pronew1 || true
                docker rm pronew1 || true
                docker run -d -p 5000:5000 --name pronew1 pronew1:latest
                '''
            }
        }
    }
}

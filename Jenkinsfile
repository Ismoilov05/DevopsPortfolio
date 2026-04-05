pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {
                git 'https://github.com/Ismoilov05/DevopsPortfolio.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t devops-app ./app'
            }
        }

        stage('Run Container') {
            steps {
                sh '''
                docker stop devops-app || true
                docker rm devops-app || true
                docker run -d -p 5000:5000 --name devops-app devops-app
                '''
            }
        }
    }
}
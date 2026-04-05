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
                sh 'docker build -t jenkins ./app'
            }
        }

        stage('Run Container') {
            steps {
                sh '''
                docker stop jenkins || true
                docker rm jenkins || true
                docker run -d -p 5000:5000 --name jenkins jenkins
                '''
            }
        }
    }
}
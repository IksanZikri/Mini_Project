pipeline {
    agent any

    stages {
        stage('Clone Repo') {
            steps {
                git 'https://github.com/kamu-user/ci-cd-demo.git'
            }
        }
        stage('Build Docker Image') {
            steps {
                script {
                    docker.build('ci-cd-demo-app', './app')
                }
            }
        }
        stage('Run Docker Compose') {
            steps {
                sh 'docker-compose up -d'
            }
        }
    }
}


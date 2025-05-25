pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/IksanZikri/Mini_Project.git'
            }
        }
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t mini-node-app .'
            }
        }
        stage('Run Docker Container') {
            steps {
                sh 'docker stop mini-node-app || true'
                sh 'docker rm mini-node-app || true'
                sh 'docker run -d --name mini-node-app -p 3000:3000 mini-node-app'
            }
        }
    }
}


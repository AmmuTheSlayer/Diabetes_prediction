pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {
                git 'https://github.com/YOUR_USERNAME/diabetes-predictor.git'
            }
        }
        stage('Build Docker Image') {
            steps {
                script {
                    dockerImage = docker.build('diabetes-ml-app')
                }
            }
        }
        stage('Run Docker') {
            steps {
                script {
                    dockerImage.run('-p 5000:5000')
                }
            }
        }
    }
}

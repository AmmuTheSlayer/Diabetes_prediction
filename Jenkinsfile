pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {
                git 'https://github.com/AmmuTheSlayer/Diabetes_prediction.git'
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

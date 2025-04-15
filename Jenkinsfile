pipeline {
    agent { label 'main' }

    stages {
        stage('Checkout') {
            steps {
                echo 'Checkout stage'
                checkout scm
            }
        }
        stage('Build') {
            steps {
                echo 'Build stage'
                npm install
            }
        }
        stage('Test') {
            steps {
                echo 'Test stage'
                npm test
            }
        }
        stage('Build Docker image') {
            steps {
                echo 'Build Docker image stage'
                docker build -t nodemain:v1.0 .
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploy stage'
            }
        }
    }
}

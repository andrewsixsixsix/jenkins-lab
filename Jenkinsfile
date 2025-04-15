pipeline {
    agent { label 'main' }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
                echo 'Checkout stage'
            }
        }
        stage('Build') {
            steps {
                echo 'Build stage'
            }
        }
        stage('Test') {
            steps {
                echo 'Test stage'
            }
        }
        stage('Build Docker image') {
            steps {
                echo 'Build Docker image stage'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploy stage'
            }
        }
    }
}

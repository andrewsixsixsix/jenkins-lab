pipeline {
    agent { label 'main' }

    tools {
        nodejs(nodeJSInstallationName: 'node')
    }

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
                sh 'npm install'
            }
        }
        stage('Test') {
            steps {
                echo 'Test stage'
                sh 'npm test'
            }
        }
        stage('Build Docker image') {
            steps {
                echo 'Build Docker image stage'
                sh 'docker build -t "nodemain:v1.0" .'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploy stage'
            }
        }
    }
}

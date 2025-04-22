pipeline {
    agent any

    tools {
        nodejs '7.8.0'
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
                script {
                    def imageTag = env.BRANCH_NAME == 'main' ? 'nodemain:v1.0' : 'nodedev:v1.0'
                    sh "docker build -t ${imageTag} ."
                }
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploy stage'
                script {
                    def isMain = env.BRANCH_NAME == 'main'
                    def imageTag = isMain ? 'nodemain:v1.0' : 'nodedev:v1.0'
                    def port = isMain ? '3000' : '3001'

                    sh "docker run -d --expose ${port} -p ${port}:3000 ${imageTag}"
                }
            }
        }
    }
}

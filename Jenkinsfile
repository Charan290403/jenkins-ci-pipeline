pipeline {
    agent any

    environment {
        DOCKER_IMAGE = "charanb123/flask-ci"
        VERSION = "v1"
    }

    stages {

        stage('Checkout Code') {
            steps {
                checkout scm
            }
        }

        stage('Build Docker Image') {
            steps {
                sh "docker build -t $DOCKER_IMAGE:$VERSION ."
            }
        }

        stage('Login to DockerHub') {
            steps {
                withCredentials([usernamePassword(
                    credentialsId: 'dockerhub-cred',
                    usernameVariable: 'USERNAME',
                    passwordVariable: 'PASSWORD'
                )]) {
                    sh "echo $PASSWORD | docker login -u $USERNAME --password-stdin"
                }
            }
        }

        stage('Push Docker Image') {
            steps {
                sh "docker push $DOCKER_IMAGE:latest"
            }
        }

    }

    post {
        success {
            echo "Pipeline Success 🚀"
        }
        failure {
            echo "Pipeline Failed ❌"
        }
    }
}

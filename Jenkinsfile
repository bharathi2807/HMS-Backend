pipeline {
    agent any

    environment {
        DOCKER_IMAGE = "hms-backend-java"
        CONTAINER_NAME = "hms-java-container"
        APP_PORT = "8080"
        NETWORK_NAME = "hms-network"
    }

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build Docker Image') {
            steps {
                sh "docker build -t ${DOCKER_IMAGE} ."
            }
        }

        stage('Deploy Container') {
            steps {
                sh """
                docker stop ${CONTAINER_NAME} || true
                docker rm -f ${CONTAINER_NAME} || true
                docker run -d --name ${CONTAINER_NAME} --network ${NETWORK_NAME} -p ${APP_PORT}:8080 ${DOCKER_IMAGE}
                """
            }
        }
    }
}

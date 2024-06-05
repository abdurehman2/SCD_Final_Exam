pipeline {
    agent any

    environment {
        // Replace with your Docker Hub username and repository
        DOCKER_HUB_USERNAME = 'abdurehman20'
        DOCKER_HUB_REPO = 'abdurehman20/scd_final_exam'
        DOCKER_IMAGE = "${DOCKER_HUB_USERNAME}/${DOCKER_HUB_REPO}"
    }

    stages {
        stage('Checkout') {
            steps {
                // Checks out the code from the GitHub repository
                git 'https://github.com/your-github-username/your-repo.git'
            }
        }

        stage('Build Docker images') {
            steps {
                // Builds the Docker images using docker-compose
                sh 'docker-compose build'
            }
        }

        stage('Login to Docker Hub') {
            steps {
                // Logs in to Docker Hub
                withCredentials([usernamePassword(credentialsId: 'dockerHubCredentials', passwordVariable: 'DOCKER_HUB_PASSWORD', usernameVariable: 'DOCKER_HUB_USERNAME')]) {
                    sh 'echo "${DOCKER_HUB_PASSWORD}" | docker login -u "${DOCKER_HUB_USERNAME}" --password-stdin'
                }
            }
        }

        stage('Push Docker images') {
            steps {
                // Tags and pushes the Docker images to Docker Hub
                sh "docker-compose push"
            }
        }
    }
}
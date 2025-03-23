pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/SRCEM-AIML/Assignment-2-c29.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t ghiyass/assignment-c2-29 .'
            }
        }

        stage('Push to Docker Hub') {
            steps {
                withDockerRegistry([credentialsId: 'docker-hub-credentials', url: '']) {
                    sh 'docker push ghiyass/assignment-c2-29'
                }
            }
        }
    }
}

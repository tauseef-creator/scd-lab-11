pipeline {
    agent any

    environment {
        DOCKER_IMAGE = 'tauseefrazaq/lab-11'
    }

    stages {
        stage('Checkout') {
            steps {
                sh 'git clone https://github.com/tauseef-creator/scd-lab-11'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh "docker build -t lab-11:1 ."
            }
        }

        stage('Run Docker Image') {
            steps {
                sh 'docker run -d -p 80:80 lab-11'
            }
        }

        stage('Push Docker Image') {
            steps {
                script {
                    docker.withRegistry('https://registry.hub.docker.com', 'docker-hub-credentials') {
                    docker.image(env.DOCKER_IMAGE).push('1')
                    }
                }
            }
        }
    }
}
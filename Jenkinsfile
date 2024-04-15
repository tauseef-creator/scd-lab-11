pipeline {
    agent any

    environment {
        DOCKER_IMAGE = 'your-dockerhub-username/your-image-name'
    }

    stages {
        stage('Checkout') {
            steps {
                // sh 'git clone https://github.com/tauseef-creator/scd-lab-11'
                sh 'echo checkout'
            }
        }

        stage('Install Dependencies') {
            steps {
                // sh 'npm install'
                sh "sleep 2m"
                sh "echo install dependencies"
            }
        }

        stage('Build Docker Image') {
            steps {
                // sh "docker build -t lab-11:1 ."
                sh "sleep 3m"
                sh "echo build image"
            }
        }

        stage('Run Docker Image') {
            steps {
                // sh 'docker run -d -p 80:80 lab-11'
                sh "sleep 1m"
                sh "echo run image"
            }
        }

        stage('Push Docker Image') {
            steps {
                script {
                    // docker.withRegistry('https://registry.hub.docker.com', 'docker-hub-credentials') {
                    //     docker.image(env.DOCKER_IMAGE).push('latest')
                    // }
                    sh "sleep 30s"
                    sh "echo push image"
                }
            }
        }
    }

    // post {
    //     always {
    //         echo 'This will always run'
    //     }
    //     success {
    //         echo 'This will run only if successful'
    //     }
    //     failure {
    //         echo 'This will run only if failed'
    //     }
    // }
}
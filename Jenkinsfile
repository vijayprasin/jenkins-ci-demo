pipeline {
    agent any

    environment {
        DOCKER_IMAGE = "Vijaykumar0502/jenkins-ci-demo"
    }

    stages {
        stage('Build Docker Image') {
            steps {
                script {
                    docker.build(DOCKER_IMAGE)
                }
            }
        }

        stage('Docker Login & Push') {
            steps {
                script {
                    docker.withRegistry('https://index.docker.io/v1/', 'dockerhub-creds') {
                        docker.image(DOCKER_IMAGE).push("latest")
                    }
                }
            }
        }
    }
}



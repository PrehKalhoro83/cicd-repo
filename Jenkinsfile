pipeline {
    agent any

    stages {
        stage('Clone Frontend') {
            steps {
                git branch: 'main', url: 'https://github.com/YOUR_USERNAME/frontend-repo.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    dockerImage = docker.build("your-dockerhub-username/frontend-app")
                }
            }
        }

        stage('Push to DockerHub') {
            steps {
                script {
                    docker.withRegistry('https://index.docker.io/v1/', 'dockerhub-credentials-id') {
                        dockerImage.push("latest")
                    }
                }
            }
        }
    }
}


"""groovey"""
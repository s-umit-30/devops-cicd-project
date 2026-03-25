pipeline {
    agent any

    stages {

        stage('Clone Code') {
            steps {
                git 'https://github.com/your-username/devops-cicd-project.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    docker.build("my-app")
                }
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker stop my-container || true'
                sh 'docker rm my-container || true'
                sh 'docker run -d -p 80:80 --name my-container my-app'
            }
        }
    }
}

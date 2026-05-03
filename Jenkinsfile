pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t myapp:latest .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker rm -f myapp || true'
                sh 'docker run -d --name myapp -p 8081:80 myapp:latest'
            }
        }
    }
}

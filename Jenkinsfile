pipeline {
    agent any

    stages {

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t mywebsite .'
            }
        }

        stage('Stop Old Container') {
            steps {
                sh 'docker rm -f vibrant_wilson || true'
            }
        }

        stage('Run New Container') {
            steps {
                sh 'docker run -d --name vibrant_wilson -p 8081:80 mywebsite'
            }
        }
    }
}

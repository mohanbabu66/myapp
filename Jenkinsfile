pipeline {
    agent any

    stages {

        stage('Clone') {
            steps {
                git 'https://github.com/USERNAME/myapp.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t mywebsite .'
            }
        }

        stage('Stop Old Container') {
            steps {
                sh 'docker rm -f mycontainer || true'
            }
        }

        stage('Run New Container') {
            steps {
                sh 'docker run -d --name mycontainer -p 8081:80 mywebsite'
            }
        }
    }
}

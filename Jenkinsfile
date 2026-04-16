pipeline {
    agent any

    stages {

        stage('Clone') {
            steps {
                echo 'Cloning...'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t my-app .'
            }
        }

        stage('Tag Image') {
            steps {
                sh 'docker tag my-app yourusername/my-app'
            }
        }

        stage('Push to DockerHub') {
            steps {
                sh 'docker push yourusername/my-app'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker run -d -p 8082:80 my-app'
            }
        }
    }
}
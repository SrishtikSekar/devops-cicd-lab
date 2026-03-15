pipeline {
    agent any

    environment {
        DOCKERHUB_CREDENTIALS = credentials('dockerhub')
    }

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/SrishtikSekar/devops-cicd-lab.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t 2023bcs0220gsrishtiksekar/2023bcs0220 .'
            }
        }

        stage('Login DockerHub') {
            steps {
                sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
            }
        }

        stage('Push Image') {
            steps {
                sh 'docker push 2023bcs0220gsrishtiksekar/2023bcs0220'
            }
        }

    }
}
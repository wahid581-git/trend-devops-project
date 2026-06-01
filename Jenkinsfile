pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/wahid581-git/trend-devops-project.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t trend-app .'
            }
        }

        stage('Deploy To Kubernetes') {
            steps {
                sh 'kubectl apply -f deployment.yaml'
                sh 'kubectl apply -f service.yaml'
            }
        }
    }
}

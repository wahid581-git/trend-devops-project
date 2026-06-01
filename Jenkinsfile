pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                echo 'Cloning Repository'
                git 'https://github.com/wahid581-git/trend-devops-project.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                echo 'Building Docker Image'
                sh 'docker build -t trend-app .'
            }
        }

        stage('Deploy To Kubernetes') {
            steps {
                echo 'Deploying To EKS'
                sh 'kubectl apply -f deployment.yaml'
                sh 'kubectl apply -f service.yaml'
            }
        }

    }
}

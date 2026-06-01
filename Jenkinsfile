pipeline {
    agent any

    stages {

        stage('Debug') {
            steps {
                sh '''
                whoami
                echo $HOME
                which aws
                which kubectl

                ls -la /var/lib/jenkins/.aws
                ls -la /var/lib/jenkins/.kube

                aws sts get-caller-identity
                kubectl get nodes
                '''
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t trend-app .'
            }
        }

        stage('Deploy To Kubernetes') {
            steps {
                sh '''
                export KUBECONFIG=/var/lib/jenkins/.kube/config

                kubectl apply -f deployment.yaml --validate=false
                kubectl apply -f service.yaml --validate=false
                '''
            }
        }

    }
}

cd ~/my-frontend-project
nano Jenkinsfile
pipeline {
    agent any

    stages {
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t frontend-app:latest .'
            }
        }

        stage('Deploy to Kubernetes') {
            steps {
                sh 'kubectl apply --validate=false -f deployment.yaml && kubectl apply --validate=false -f service.yaml'
            }
        }
    }
}


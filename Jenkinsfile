    agent any

    stages {

        stage('Checkout') {
            steps {
                git 'https://github.com/Nithees28/pipelineserver.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t frontend-app:latest .'
            }
        }

        stage('Deploy to Kubernetes') {
            steps {
                sh '''
                  kubectl apply -f deployment.yaml
                  kubectl apply -f service.yaml
                '''
            }
        }
    }
}

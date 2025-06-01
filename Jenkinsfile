pipeline {
    agent any

    environment {
        KUBECONFIG = "C:/Users/prati/.kube/config" // Use forward slashes for cross-platform compatibility
    }

    stages {
        stage('Checkout') {
            steps {
                echo '🔄 Checking out code from GitHub...'
                git branch: 'main', url: 'https://github.com/pratik-baibhav/Flask-CI-CD-project.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                echo '🐳 Building Docker image...'
                sh 'docker build -t flaskapp:latest .'
            }
        }

        stage('Deploy to Minikube') {
            steps {
                echo '🚀 Deploying to local Minikube cluster...'
                sh '''
                    echo "Using kubeconfig: $KUBECONFIG"
                    export KUBECONFIG=$KUBECONFIG
                    kubectl get nodes
                    kubectl apply -f deployment.yaml
                    kubectl apply -f service.yaml
                '''
            }
        }
    }

    post {
        success {
            echo '✅ Deployment completed successfully!'
        }
        failure {
            echo '❌ Deployment failed. Check logs for details.'
        }
    }
}

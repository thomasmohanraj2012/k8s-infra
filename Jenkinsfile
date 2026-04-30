pipeline {
    agent any
    stages {
        stage('Build Image') {
            steps {
                script {
                    docker.build("myapp:latest")
                }
            }
        }
        stage('Test') {
            steps {
                sh 'echo "Running tests..."'
            }
        }
        stage('Deploy to Kubernetes') {
            steps {
                sh 'kubectl apply -f k8s-infra/wordpress/deployment.yaml'
            }
        }
    }
}

pipeline {
    agent any

    environment {
        DOCKERHUB_CREDENTIALS = credentials('dockerhub-creds')
        KUBECONFIG = 'C:\\Users\\DELL\\.kube\\config'
    }

    stages {
        stage('Checkout Code') {
            steps {
                echo "Checking out code from GitHub..."
                git branch: 'main', url: 'https://github.com/shivshankar66/delhi-metro-app.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                echo "Building Docker image..."
                bat "docker build -t shivam193/delhi-metro1:%BUILD_NUMBER% -t shivam193/delhi-metro1:latest D:\\Users\\DELL\\Downloads\\Delhi metro"
            }
        }

        stage('Push Docker Image') {
            steps {
                echo "Pushing Docker image to DockerHub..."
                withCredentials([usernamePassword(credentialsId: 'dockerhub-creds', usernameVariable: 'DOCKER_USER', passwordVariable: 'DOCKER_PASS')]) {
                    bat 'echo %DOCKER_PASS% | docker login -u %DOCKER_USER% --password-stdin'
                    bat "docker push shivam193/delhi-metro1:%BUILD_NUMBER%"
                    bat "docker push shivam193/delhi-metro1:latest"
                }
            }
        }

        stage('Deploy to Minikube') {
            steps {
                echo "Deploying to Minikube..."
                bat "kubectl --kubeconfig=%KUBECONFIG% apply -f D:\\Users\\DELL\\Downloads\\Delhi metro\\deloy-service.yml"
            }
        }

        stage('Verify Deployment') {
            steps {
                echo "Checking pods and services..."
                bat "kubectl --kubeconfig=%KUBECONFIG% get pods -o wide"
                bat "kubectl --kubeconfig=%KUBECONFIG% get svc"
            }
        }
    }
}

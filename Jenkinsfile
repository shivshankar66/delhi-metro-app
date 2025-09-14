pipeline {
    agent any

    environment {
        DOCKERHUB_CREDENTIALS = credentials('dockerhub-creds')   // Jenkins me DockerHub creds
        KUBECONFIG = "C:\\Users\\DELL\\.kube\\config"           // Windows me Minikube kubeconfig path
        IMAGE_NAME = "shivam193/delhi-metro1"
    }

    stages {

        stage('Checkout Code') {
            steps {
                echo 'Checking out code from GitHub...'
                git branch: 'main',
                    url: 'https://github.com/shivshankar66/delhi-metro-app.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                echo 'Building Docker image...'
                bat """
                docker build -t %IMAGE_NAME%:%BUILD_NUMBER% -t %IMAGE_NAME%:latest "D:\\Users\\DELL\\Downloads\\Delhi metro"
                """
            }
        }

        stage('Push Docker Image') {
            steps {
                echo 'Pushing Docker image to DockerHub...'
                withCredentials([usernamePassword(credentialsId: 'dockerhub-creds', usernameVariable: 'DOCKER_USER', passwordVariable: 'DOCKER_PASS')]) {
                    bat """
                    echo %DOCKER_PASS% | docker login -u %DOCKER_USER% --password-stdin
                    docker push %IMAGE_NAME%:%BUILD_NUMBER%
                    docker push %IMAGE_NAME%:latest
                    """
                }
            }
        }

        stage('Deploy to Minikube') {
            steps {
                echo 'Deploying to Kubernetes (Minikube)...'
                bat 'kubectl apply -f "D:\\Users\\DELL\\Downloads\\Delhi metro\\deloy-service.yml"'
            }
        }

        stage('Verify Deployment') {
            steps {
                echo 'Checking deployed service...'
                bat 'kubectl get svc metro-svc'
                bat 'kubectl get pods -l app=metro'
            }
        }

    }

    post {
        always {
            echo 'Cleaning up...'
            bat 'docker logout'
        }
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed. Check logs for errors.'
        }
    }
}

pipeline {
    agent any

    environment {
        IMAGE_NAME = "fastapi-app"
        CONTAINER_NAME = "fastapi-container"
    }

    stages {

        stage('Clone Repository') {
            steps {
                git branch: 'devops-assignment-Prathamesh-Salokhe',
                    url: 'https://github.com/Prathamesh5152/docker-fastapi-test.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t $IMAGE_NAME .'
            }
        }

        stage('Stop Old Container') {
            steps {
                sh '''
                docker stop $CONTAINER_NAME || true
                docker rm $CONTAINER_NAME || true
                '''
            }
        }

        stage('Run Container') {
            steps {
                sh '''
                docker run -d \
                  -p 8000:8000 \
                  -v $(pwd)/app/data:/app/app/data \
                  --name $CONTAINER_NAME \
                  $IMAGE_NAME
                '''
            }
        }

    }

    post {
        success {
            echo "Deployment Successful!"
        }
        failure {
            echo "Deployment Failed!"
        }
    }
}
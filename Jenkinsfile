pipeline {
    agent any
    environment {
        DOCKER_COMPOSE_FILE = "docker-compose.yml"
    }
    stages {
        stage("Pull Latest Images") {
            steps {
                sh "docker-compose pull"
            }
        }
        stage("Deploy Services") {
            steps {
                sh "docker-compose down"
                sh "docker-compose up -d"
            }
        }
    }
    post {
        success {
            echo "Services deployed successfully!"
        }
        failure {
            echo "Deployment failed."
        }
    }
}

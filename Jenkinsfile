pipeline {
    agent {
        label 'agent-with-ssh'
    }
    environment {
        compose_service_name = "flask-jenkins"
        workspace = "/home/sharthu/project/flask-jenkins/"
    }
    stages {
        stage('Build & Run Containers') {
            steps {
                sh 'docker-compose down || true'
                sh 'docker-compose up -d --build'
            }
        }
    }
    post {
        success {
            echo 'Application deployed successfully!'
        }
        failure {
            echo 'Deployment failed.'
        }
    }
}

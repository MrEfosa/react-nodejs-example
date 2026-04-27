pipeline {
    agent any

    stages {

        stage('Test') {
            steps {
              echo "testing application ..."
            }
        }

        stage('Build Docker Image') {
            steps {
              echo "building application"
            }
        }

        stage('Deploy Container') {
            steps {
              echo "deploying app ..."
            }
        }
    }

    post {
        success {
            echo 'Deployment successful!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}

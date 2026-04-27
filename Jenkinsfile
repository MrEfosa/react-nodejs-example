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

        stage('Deploy') {
            steps {
                def dockerCmd = 'docker run -d -p 80:80  sirdavidchris/demo-app:1.0'
              sshagent(['ec2-server-key']) {
                    sh "ssh -o StrictHostKeyChecking=no ec2-user@100.52.234.62 ${dockerCmd}"
                 }
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

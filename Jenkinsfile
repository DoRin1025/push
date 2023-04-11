pipeline {
    agent any
    environment {
        DOCKERHUB_CREDENTIALS = credentials('dockerRegistry')
    }
    stages {
        stage('Build Docker') {
            steps {
               echo 'Urrraa'
            }
        post {
            success {
                slackSend color: 'good', message: 'Succes'
            }
            failure {
                slackSend color: 'danger', message: 'Error'
            }
        }
            
        }
    }
}

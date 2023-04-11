pipeline {
    agent any
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

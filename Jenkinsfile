pipeline {
    agent any
    stages {
        stage('Build Docker') {
            steps {
                sh 'docker image build -t test-docker .'
            }
        }
    }
}

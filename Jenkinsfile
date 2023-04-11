pipeline {
    agent any
    stages {
        stage('Build Docker') {
            steps {
                sh 'docker image build -t test-docker .'
                sh 'docker push registry.ismartapps.com.au:5000/test-docker:latest'
            }
        }
    }
}

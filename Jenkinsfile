pipeline {
    agent any
    stages {
        stage('Build Docker') {
            steps {
                sh 'docker image build -t test-docker .'
                sh 'docker login registry.ismartapps.com.au:5000 -u registry.user -p 7MVvYhAem7y6bbvD'
                sh 'docker push registry.ismartapps.com.au:5000/test-docker:latest'
            }
        }
    }
}

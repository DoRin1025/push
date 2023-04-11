pipeline {
    agent any
    environment {
        DOCKERHUB_CREDENTIALS = credentials('dockerRegistry')
    }
    stages {
        stage('Login') {
            steps {
                 sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login registry.ismartapps.com.au:5000 -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
            }
        }
        stage('Build Docker') {
            steps {
               sh 'docker push registry.ismartapps.com.au:5000/test-docker:latest'
            }
        }
    }
}

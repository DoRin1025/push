pipeline {
    agent any
    stages {
        stage('Build Docker') {
            steps {
               script {
                     docker.build registry + ":$BUILD_NUMBER"
                 }
            }
        }
    }
}

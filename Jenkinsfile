pipeline {
    agent any
    stages {
        stage('Example Deploy Main') {
            when {
                branch 'main'
            }
            steps {
                echo 'Deploying'
            }
        }
        stage('Example Deploy DEV') {
            when {
                branch 'dev'
            }
            steps {

                 echo 'Urrraa'
            }
			
		post {
            success {
                slackSend color: 'good', message: "Build successfully deployed on is-android-test  - ${env.JOB_NAME} ${env.BUILD_NUMBER} (<${env.BUILD_URL}|Open>) Good job!"
            }
            failure {
                slackSend color: 'danger', message: 'Error'
            }
            unstable {
                slackSend color: 'warning', message: 'Warning'
            }

        }	
        }
    }
}

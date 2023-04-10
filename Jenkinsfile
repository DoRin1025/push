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
                script{

                    command='''
		        ls ./dev
                        cd ./dev/
                        git pull origin dev
                    '''
                  // Execute commands
                  sshPublisher(publishers: [
				         sshPublisherDesc(
						 configName: 'Instance-2',
						 verbose: true,
                         transfers: [ sshTransfer(execCommand: command    )])])
						 
				   flag = true
                     
                }
            }
			
        }
        
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

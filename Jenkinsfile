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
                     
                    cleanWs()
                    echo 'Local files.....'       
                    sh 'ls -l'
 
                    command='''
                        cd ./dev/
                        git pull origin deffv
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
			
		post {
            success {
                slackSend color: 'good', message: 'Succes'
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

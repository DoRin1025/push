pipeline {
    agent any
    stages {
        stage('Example Build') {
            steps {
                echo 'Hello World'
            }
        }
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
                        git pull origin gfdd
                    '''
                  // Execute commands
                  sshPublisher(publishers: [
				         sshPublisherDesc(
						 configName: 'Instance-2',
						 verbose: true,
                         transfers: [ sshTransfer(execCommand: command    )])])
                     
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
            unstable {
	    	slackSend color: 'warning', message: 'Warning'
	    }
        }
}

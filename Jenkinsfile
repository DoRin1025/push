def flag = false;
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
                        git pull origin dffev
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
		stage('3 - If Maybe was executed') {
            when { expression { flag == true } }

            steps {
                slackSend color: 'good', message: 'Succes'
            }
        }
        
    }
}

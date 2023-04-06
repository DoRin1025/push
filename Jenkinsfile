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
                echo 'Deploying to Main'
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
                        hostname
                        ls -l
                        date
                        touch prod/test.file
                    '''
                  // Execute commands
                  sshPublisher(publishers: [sshPublisherDesc(configName: 'Instance-2',
                    transfers: [ sshTransfer(execCommand: command    )])])
                     
                }
            }
        }
    }
}

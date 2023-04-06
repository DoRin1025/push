pipeline {
    agent any
    stages {
        stage('ssh') {
            steps {
                script{
                     
                    cleanWs()
                    echo 'Local files.....'       
                    sh 'ls -l'
 
                    command='''
                        touch test.txt
                    '''
                  // Execute commands
                  sshPublisher(publishers: [sshPublisherDesc(configName: 'Instance-2',
                    transfers: [ sshTransfer(execCommand: command    )])])
                     
                }
            }
        }
    }
         
}

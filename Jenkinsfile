pipeline {
    agent any
	stages {
        stage('Example') {
		    when { branch 'main' }
            steps {
                echo 'This is not master or staging'
                
            }
        }
    }
}

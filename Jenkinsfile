pipeline {
    agent any
	stages {
        stage('Example') {
            when { 
		    beforeOptions true
		    branch 'dev' 
	    }
            steps {
                echo 'This is not master or staging'
                
            }
        }
    }
}

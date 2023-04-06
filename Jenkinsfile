pipeline {
    agent any
	stages {
        stage('Example') {
            when { 
		    beforeOptions true
		    branch 'main' 
	    }
            steps {
                echo 'This is not master or staging'
                
            }
        }
    }
}

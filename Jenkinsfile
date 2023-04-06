pipeline {
    agent any
	stages {
        stage('Example') {
            steps {
                script { 
                    if (env.BRANCH_NAME == 'master') {
                        echo 'This is master'
                    } else {
                        echo 'things and stuff'
                    }
                }
            }
        }
    }
}

pipeline {
    agent any
	stages {
        stage('Example') {
            steps {
                script { 
                    if (env.BRANCH_NAME != 'main') {
                        echo 'This is main env.BRANCH_NAME'
                    } else {
                        echo 'This is not main env.BRANCH_NAME'
                    }
                }
            }
        }
    }
}

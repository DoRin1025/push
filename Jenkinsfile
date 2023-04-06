pipeline {
    agent any
    stage('Example') {
        steps {
            script { 
                if (env.BRANCH_NAME != 'master') {
                    echo 'This is not master or staging'
                } else {
                    echo 'things and stuff'
                }
            }
        }
    }
}

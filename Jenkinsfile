pipeline {
    agent any
    stages('Example') {
        steps {
            script { 
                if (env.BRANCH_NAME != 'main') {
                    echo 'This is not master or staging'
                } else {
                    echo 'things and stuff'
                }
            }
        }
    }
}

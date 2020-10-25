pipeline {
    agent any


    stages {

        stage('Smoke') {
            steps {
                script {
                    def myVariable = true
                    echo "Running ${env.BUILD_ID} ---> ${env.BRANCH_NAME}"
//                    if (Math.random() > 0.5)
//                        myVariable = true

                    if (myVariable)
                        input 'All good?'
                }
            }
        }
    }

}

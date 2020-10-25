pipeline {
    agent any

    def myVariable = false
    stages {

        stage('Smoke') {
            steps {
                script {
                    echo "Running ${env.BUILD_ID} ---> ${env.BRANCH_NAME}"
                    if (Math.random() > 0.5)
                        myVariable = true

                    if (myVariable)
                        input 'All good?'
                }
            }
        }
    }

}

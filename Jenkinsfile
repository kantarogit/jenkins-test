pipeline {
    agent any

    stages {
        stage('Smoke') {
            try {
                steps {
                    echo "Running ${env.BUILD_ID} ---> ${env.BRANCH_NAME}"
                    if (Math.random() > 0.5)
                        currentBuild.result = 'FAILURE'
                }
            }
            catch (err) {
                echo err
                input 'All good?'
            }

        }
    }
}
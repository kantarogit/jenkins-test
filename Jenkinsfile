pipeline {
    agent any

    stages {
        stage('Smoke') {
            steps {
                echo "Running ${env.BUILD_ID} ---> ${env.BRANCH_NAME}"
            }
        }
    }
}
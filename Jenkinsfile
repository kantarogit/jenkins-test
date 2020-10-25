pipeline {
    agent any
    stages {

        stage('Smoke') {
            steps {
                script {
                    echo "Tests running..."
                    sh "exit 1"
                }
            }
        }

    }

    post {
        failure {
            steps {
                input 'All fine?'
                currentBuild.result = "SUCCESS"

            }

        }
        success {
            echo "Success!"
        }
    }
}


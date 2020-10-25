pipeline {
    agent any


    stages {

        stage('Smoke') {
            steps {
                echo "Tests running..."
                sh "exit 1"
            }
        }
    }

    post {
        failure {
            steps {
                input 'All fine?'
                script {
                    currentBuild.result = 'SUCCESS'
                }
            }

        }
        success {
            echo "Success!"
        }
    }
}


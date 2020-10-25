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
            input 'All fine?'
            steps {
                currentBuild.result = 'SUCCESS'
            }

        }
        success {
            echo "Success!"
        }
    }
}


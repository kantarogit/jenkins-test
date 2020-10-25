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
            currentBuild.result = 'SUCCESS'
        }
        success {
            echo "Success!"
        }
    }
}


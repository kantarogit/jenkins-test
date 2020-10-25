pipeline {
    agent any


    stages {

        stage('Smoke') {
            steps {
                catchError(buildResult: 'SUCCESS', stageResult: 'FAILURE') {
                    echo "Tests running..."
                    sh "exit 1"
                }
            }
        }
    }

    post {
        failure {
            input 'All fine?'
        }
        success {
            echo "Success!"
        }
    }
}


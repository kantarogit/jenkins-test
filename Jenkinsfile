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
            echo 'approved'

            script { currentBuild.buildResult = 'SUCCESS' }

        }
    }
}


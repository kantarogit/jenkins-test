pipeline {
    agent any

//    environment {
//        cont = 'false'
//    }
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
            script {
                timeout(time: 60, unit: 'SECONDS') {
                    input(message: 'Approve anyway')
                    currentBuild.result = 'SUCCESS'
                }
            }
        }
    }
}


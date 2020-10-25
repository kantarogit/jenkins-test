pipeline {
    agent any


    stages {

        stage('Smoke') {
            steps {
                echo "Smoke tests running..."
                sh 'exit 1'
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

}

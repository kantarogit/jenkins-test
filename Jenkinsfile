pipeline {
    agent any

    environment {
        cont = 'true'
    }
    stages {

        stage('Smoke') {
            steps {
                script {
                    try {
                        echo "Tests running..."
                        sh "exit 1"
                    } catch (Error e) {
                        echo 'error handling' + e
                        env.cont = 'false'
                    }
                }
            }
        }

        stage('Publish') {
            when { environment name: 'cont', value: 'false' }
            steps {
                timeout(time: 60, unit: 'SECONDS') {
                    input(message: 'Approve anyway')
                }
                script { currentBuild.result = 'SUCCESS' }
            }

        }

    }
}


pipeline {
    agent any

    environment {
        cont = 'false'
    }
    stages {

        stage('Smoke') {
            steps {
                script {
                    try {
                        echo "Tests running..."
                        sh "exit 1"
                    } catch (e) {
                        echo 'error handling'
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


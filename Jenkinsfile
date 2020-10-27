pipeline {
    agent any

    stages {

        stage('Smoke') {
            steps {
                script {
                    try {
                        echo "Tests running..."
                        sh "exit 0"
                    } catch (e) {
                        env.failedStage = 'true'
                    }
                }
            }
        }

        stage('QA Approval') {
            when {
                environment name: 'failedStage', value: 'true'
            }

            steps {
                timeout(time: 60, unit: 'SECONDS') {
                    input(message: 'Approve anyway')
                    script {currentBuild.result = 'SUCCESS'}
                }
            }
        }
    }
}

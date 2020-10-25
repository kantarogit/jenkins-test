pipeline {
    agent any

    environment {
        cont = true
    }
    stages {

        stage('Smoke') {
            steps {
                try {
                    echo "Tests running..."
                    sh "exit 1"
                } catch (Error e) {
                    echo 'error handling' + e
                    env.cont = false
                }
            }
        }

        stage('Publish') {
            when {
                env.cont == false
            }
                steps {
                    timeout(time: 60, unit: 'SECONDS') {
                        input(message: 'Approve anyway')
                    }
                    currentBuild.result = 'SUCCESS'
                }

        }

    }
}


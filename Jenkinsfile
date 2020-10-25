pipeline {
    agent any

    environment {
        ALL_FINE = true
    }


    stages {

        stage('Smoke') {
            steps {
                script {
                    try {
                        echo "Tests running..."
                        sh "exit 1"
                    }
                    catch (Exception e) {
                        echo e
                        env.ALL_FINE = false
                    }
                }
            }
        }

        stage('Approval') {
            when{
                env.ALL_FINE == false
            }
            steps {
                input 'All fine?'
            }
        }
    }

//    post {
//        failure {
//            steps {
//                input 'All fine?'
//                script {
//                    currentBuild.result = 'SUCCESS'
//                }
//            }
//
//        }
//        success {
//            echo "Success!"
//        }
//    }
}


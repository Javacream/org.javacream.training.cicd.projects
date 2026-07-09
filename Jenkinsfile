pipeline {
    agent none

    environment {
        BUILD_VERSION = '35'
    }

    stages {
        stage('Parallel Stage') {
            parallel {
                stage('Hello') {
                    agent { label 'generic' }
                    steps {
                        echo 'Hello World'
                    }
                }
                stage('Goodbye') {
                    agent { label 'java' }
                    steps {
                        echo 'Goodbye'
                    }
                }
            }
        }

        stage('Version') {
            agent { label 'generic' }
            when {
                environment name: 'BUILD_VERSION', value: '35'
            }
            steps {
                echo "BUILD_VERSION is ${BUILD_VERSION}"
            }
        }

        stage('WrongVersion') {
            agent { label 'generic' }
            when {
                environment name: 'BUILD_VERSION', value: '20'
            }
            steps {
                echo "BUILD_VERSION is ${BUILD_VERSION}"
            }
        }
    }

    post {
        always {
            echo 'always - Run the steps in the post section regardless of the completion status'
        }
        success {
            echo 'success - all stages passed'
        }
        failure {
            echo 'failure-something went wrong'
        }
    }
}

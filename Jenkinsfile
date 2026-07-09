pipeline {
    agent any

    environment {
        DEPLOY_ENV = 'prod'
    }

    stages {
        stage('Prod') {
            when {
                environment name: 'DEPLOY_ENV', value: 'prod'
            }
            steps {
                echo 'Hello World from Prod'
            }
        }
        stage('Dev') {
            when {
                environment name: 'DEPLOY_ENV', value: 'dev'
            }
            steps {
                echo 'Hello World from Dev'
            }
        }
    }
    post
    {
        always {
            echo 'This will always run'
        }
        success {
            echo 'This will run only if successful'
        }
        failure {
            echo 'This will run only if failed'
        }
        fixed {
            echo 'This will run only if the build was previously failing but is now successful'
        }
    }
}

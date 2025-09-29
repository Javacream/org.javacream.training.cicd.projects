pipeline {
    agent any

    stages {
        stage('Stage 1') {
            steps {
                echo 'Stage 1'
            }
        }
        stage('Stage 2') {
            steps {
                echo 'Stage 2'
            }
        }
        stage('Stage 3') {
            steps {
                echo 'Stage 3'
            }
        }
    }

    post {
        success {
            echo "Pipeline was successful"
        }
        failure {
            echo "Something really bad happened, DO SOMETHING!!!"
        }
    }
}

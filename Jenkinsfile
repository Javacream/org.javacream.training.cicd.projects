pipeline {
    agent any

    environment {
        globalVar = 'Globaler Text'
    }

    stages {
        stage('Start') {

            environment {
                startVar = 'Variable von Start'
            }

            steps {
                echo "${startVar}"
            }
        }
        stage('Middle') {

            when {
                branch 'hopfhauer_29092025'
            }

            environment {
                middleVar = 'Variable von Middle'
            }

            steps {
                echo "${middleVar}"
            }
        }
        stage('End') {

            steps {
                echo "${globalVar}"
            }
        }
    }

    post {
        always {
            echo "${globalVar}"
            sh 'printenv'
        }

    }
}

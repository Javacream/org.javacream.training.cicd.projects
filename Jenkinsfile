pipeline {
    agent any

    globalVar = 'Globaler Text'

    stages {
        stage('Start') {

            startVar = 'Variable von Start'

            steps {
                echo "${startVar}"
            }
        }
        stage('Middle') {

            when {
                branch 'hopfhauer_29092025'
            }

            middleVar = 'Variable von Middle'

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
            globalVar = 'Ende'
            echo "${globalVar}"
            sh 'printenv'
        }

    }
}

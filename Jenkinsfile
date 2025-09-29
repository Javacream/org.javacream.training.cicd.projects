pipeline {
    agent any
    environment {
        NAME = 'Sawitzki'
    }
    stages {

        stage('Stage 1') {
            environment {
                FIRSTNAME = 'Rainer'
                FIRSTNAME2 = 'Ulrich'
            }
            steps {
                echo "Hello ${FIRSTNAME} ${FIRSTNAME2} ${NAME} from Stage 1"
            }
        }
        stage('Stage 2') {
            steps {
                echo "Hello ${NAME} from Stage 2"
            }
        }
        stage('Stage 3') {
            when {expression {env.FIRSTNAME != null}}
            steps {
                echo "Hello ${FIRSTNAME} ${NAME} from Stage 2"
                sh 'ls -l'
            }
        }
    }
    post{
        always {
            echo 'always'
            sh 'printenv'

        }
        success {
            echo 'success'
            
        }

        failure {
            echo 'failure'
            
        }

    }
}

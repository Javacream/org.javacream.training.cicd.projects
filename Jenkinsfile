pipeline {
    agent none
    environment {
        hello_message = 'Hello Pipeline'
        goodbye_message = 'Goodbye Pipeline'

    }
    stages {
        stage('Hello') {
            agent {label 'generic'}
            steps {
                echo "${env.hello_message}"
            }
        }
        stage('Goodbye') {
            agent {label 'java'}
            steps {
                echo "${env.goodbye_message}"
            }
        }
    }
    post { 
        always { 
            echo 'I will always say Hello again!'
        }
        success { 
            echo 'it is a successfull pipeline run'
        }
        failure { 
            echo 'it is a failed pipeline run'
        }
        fixed { 
            echo 'it is a fixed pipeline run'
        }

    }
}


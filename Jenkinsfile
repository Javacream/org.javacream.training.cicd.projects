pipeline {
    agent none

    stages {
        stage('Hello') {
            agent {label 'generic'}
            steps {
                echo 'Hello World'
            }
        }
        stage('Goodbye') {
            agent {label 'java'}
            steps {
                echo 'Goodbye'
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


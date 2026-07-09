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
}


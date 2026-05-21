pipeline {
    agent none
    stages {
        stage('Hello') {
            agent {
                label 'kr-test-agent'
            }
            steps {
                echo 'Hello World'
            }
        }
        stage('Kuckuck') {
            agent {
                label 'python'
            }
            steps {
                echo 'Kuckuck, fiep fiep!'
            }
        }
    }
}

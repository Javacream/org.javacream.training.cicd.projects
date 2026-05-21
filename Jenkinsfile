pipeline {
    agent none
    parallel {
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
    post { 
        always { 
            echo 'I will always say Hello again!'
        }
    }
}

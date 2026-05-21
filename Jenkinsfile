pipeline {
    agent none
    environment { // accessible to all stages
        HELLO = 'WORLD'
    }
    stages {
        stage('parallel') {
            parallel {
                stage('Hello') {
                    agent {
                        label 'kr-test-agent'
                    }
                    steps {
                        echo 'Hello World'
                        echo env.HELLO
                    }
                }
                stage('Kuckuck') {
                    agent {
                        label 'python'
                    }
                    steps {
                        echo 'Kuckuck, fiep fiep!'
                        echo env.GIT_BRANCH
                        echo env.BUILD_TAG
                    }
                }
            }
        }
    }
    post { 
        always { 
            echo 'I will always say Hello again!'
        }
    }
}

pipeline {
    agent none
    environment { // accessible to all stages
        HELLO = 'WORLD'
    }
    stages {
        stage('Hello') {
            agent {
                label 'kr-test-agent'
            }
            steps {
                echo 'Hello World'
                echo env.HELLO
                sh 'ls -l'
                sh 'pwd'
                sh 'touch testfile'
                stash includes: 'testfile', name: 'Files'
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
                sh 'ls -l'
                unstash 'Files'
                sh 'ls -l'
            }
        }
    }
    post { 
        always { 
            echo 'I will always say Hello again!'
        }
    }
}

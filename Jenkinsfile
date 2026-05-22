pipeline {
    agent none
    environment {
        MESSAGE = 'Start parallel stage'
    }    
    stages {
        stage('Parallel Stage') {
            parallel {
                stage('Build') {
                   agent {
                        label 'python'
                    }
                    steps {
                        echo env.MESSAGE
                        sh 'python -V'
                    }
                }
                stage('Test') {
                    agent {
                        label 'java'
                    }
                    steps {
                        sh 'mvn -version'
                    }
                }
          }
    }
        stage ('Stash') {
            agent {
                label 'python'
            }
            steps {
                echo 'Stash'
                writeFile(
                    file: 'foo.txt',
                    text: 'foo'
                    )
                 writeFile(
                    file: 'bar.txt',
                    text: 'bar'
                    )
                stash(
                    name: 'foo',
                    includes: 'foo.txt'
                    )
                
                sh 'ls'
            }
        }
        stage ('Unstash') {
            agent {
                label 'java'
            }
            steps {
                echo 'Unstash'
                unstash ('foo')
                sh 'ls'
            }
        }
}
post {
    success {
        echo 'Build erforlgreich'
    }
    failure {
        echo 'Fehler aufgetreten'
    }
}
}

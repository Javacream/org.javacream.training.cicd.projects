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
                    name: 'foo.txt'
                    text: 'foo'
                    )
                sh 'ls'
                echo 'Inhalt von bar.txt' >bar.txt
                stash(
                    name: 'foo'
                    includes: 'foo.txt'
                    )
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

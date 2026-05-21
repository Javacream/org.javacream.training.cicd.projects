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
                label 'generic'
            }
            steps {
                echo 'Stash'
                echo 'Inhalt von foo.txt' >foo.txt
                echo 'Inhalt von bar.txt' >bar.txt
                stash foo.txt
            }
        }
        stage ('Unstash') {
            agent {
                label 'generic'
            }
            steps {
                echo 'Unstash'
                unstash foo.txt
                cat foo.txt
                cat bar.txt
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

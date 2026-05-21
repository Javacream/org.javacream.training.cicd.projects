pipeline {
    agent none
    environment { 
        CC = 'clang'
        VERSION = "1.0"
    }
    stages {
        stage('Parallel Stage') {
            parallel {
                stage('Build') {
                   agent {
                        label 'python'
                    }
                    steps {
                        echo "Version ${VERSION}"
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
    stage('Test stash') {
            agent {
                  label 'java'
            }

            steps {
                sh 'mkdir -p build'
                sh 'echo "Hallo Jenkins" > build/output.txt'

                stash(
                    name: 'build-artifacts',
                    includes: 'build/**'
                )
            }
        }
        stage('Test unstash') {
            agent {
                 label 'java'
            }

            steps {
                unstash 'build-artifacts'

                sh 'cat build/output.txt'
                sh 'echo "Deployment erfolgreich"'
            }
        }
    }
post {
    success {
        echo 'Pipeline erfolgreich'
    }
    failure {
        echo 'Pipeline fehlgeschlagen'
    }
}
}

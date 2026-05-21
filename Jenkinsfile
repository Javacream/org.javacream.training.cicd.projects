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
                        echo $MESSAGE
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
        stage ('Sequential Stage') {
            agent {
                label 'generic'
            }
            steps {
                echo 'Sequential Stage'
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

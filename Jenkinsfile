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
                    echo 'Sequential Stage'
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

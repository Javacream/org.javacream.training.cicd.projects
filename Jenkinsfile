pipeline {
    agent none
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

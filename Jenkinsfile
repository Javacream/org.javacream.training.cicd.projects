ipeline {
    agent none

    stages {
        stage('Parallel Stage') {
            parallel {
                stage('Python') {
                   agent {
                        label 'python'
                    }
                    steps {
                        sh 'python --version'
                    }
                }
                stage('Java') {
                    agent {
                        label 'java'
                    }
                    steps {
                        sh 'java --version'
                        sh 'mvn --version'
                    }
                }
            }
        }
    }

    post {
        success {
            echo 'SUCCESS'
        }
        failure {
            echo 'FAILURE'
        }
    }   
}

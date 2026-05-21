pipeline {
    agent none
    
    environment{
        GREETING = 'Hello World'
        GOODBYE = 'Bye-Bye World'
    }
    
    stages {
        stage ('Sequential START') {
            agent any
            steps {
                echo "${GREETING}"
            }
        }
        
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
        
        stage ('Sequential END') {
            agent any
            steps {
                echo "${GOODBYE}"
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

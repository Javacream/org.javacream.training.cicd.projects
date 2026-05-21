pipeline {
    agent none
    
    environment{
        GREETING = 'Hello World'
        GOODBYE = 'Bye-Bye World'
        FILE1 = 'file1.txt'
        FILE2 = 'file2.txt'
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

        stage ('Create Stash') {
            agent {
                label 'python'
            }
            steps {
                writeFile(
                    file: "${FILE1}",
                    text: "${GREETING}"
                )
                writeFile(
                    file: "${FILE2}",
                    text: "${GOODBYE}"
                )
                sh 'ls -lha'
                sh 'cat "${FILE1}"'
                sh 'cat "${FILE2}"'
                stash (
                    name: 'mystash',
                    includes: "${FILE1}"
                )
            }
        }

        stage ('Read Stash') {
            agent {
                label 'java'
            }
            steps {
                unsash('mystash')
                sh 'ls -lha'
                sh cat "${FILE1}"
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

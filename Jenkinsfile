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
            agent any
            steps {
                echo "${GREETING}" > "${FILE1}"
                echo "${GOODBYE}" > "${FILE2}"
                sh cat "${FILE1}"
                sh cat "${FILE2}"
                stash "${FILE1}"
            }
        }

        stage ('Read Stash') {
            agent any
            steps {
                unsash "${FILE1}"
                script {
                    if (fileExists("${FILE1}")) {
                        echo "SUCCESS: ${FILE1} exists"
                    }
                    if (fileExists("${FILE2}")) {
                        echo "FAILURE: ${FILE2} exists"
                    }
                }
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

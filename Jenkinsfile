pipeline {
    agent none
    environment{
        MESSAGE = 'start sequential'
    }
    stages {
        stage('Start sequential') {
            agent any
            steps {
                echo "$MESSAGE"
            }
        }
        stage('Parallel executions'){
            parallel{
                stage('Hello Python') {
                    agent {
                        label 'python'
                    }
                    steps {
                        sh 'python -V'
                    }
                }
                stage('Hello Java') {
                    agent {
                        label 'java'
                    }
                    steps {
                        sh 'mvn -version'
                    }
                    post { 
                        always { 
                                echo 'post: always in Java'
                            }
                    }
                }    
            }
        }
        stage('Finish sequential') {
            agent any
            steps {
                echo "finish sequential on job ${env.JOB_NAME}"
                sh 'echo "sequential on job $JOB_NAME"'
            }
        }
    }
    post { 
            success { 
                echo 'post success in pipeline'
            }
            failure { 
                echo 'post failure in pipeline'
            }
    }
}

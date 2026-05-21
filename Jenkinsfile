pipeline {
    agent none

    stages {
        stage('Start sequential') {
            agent any
            steps {
                echo 'start sequential'
            }
        }
        stage('Parallel eecutions'){
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
                echo 'finish sequential'
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

pipeline {
    agent none 
    parameters {
        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
    }
    environment { 
        CC = 'TAN'
    }
    stages {
        stage('Print was aus ...') {
            parallel {
                stage('--001---') {
                    agent { label 'java' }
                    steps { echo 'Hallo JAVA' 
                        sh 'java -version'
                    }
                }
                stage('--002---') {
                    agent { label 'python' }
                    steps { echo 'Hallo PYTHON' 
                        sh 'python --version'
                        echo "Choice: ${params.CHOICE}"
                    }
                }
                stage('--003---') {
                    agent { label 'java' }
                    steps { echo 'Hallo MAVEN'
                        sh 'mvn -version'
                    }
                 post { 
                    always { 
                        echo 'I will always say Hello again!'
                    }
                 }
                }
                stage('Environment') {                
                    steps {
                        echo "${CC}"
                        echo $GIT_AUTHOR_NAME
                    }
                }
            }
        }
    }
    post { 
        always { 
            echo 'I will always say Hello again!'
        }
    }
}

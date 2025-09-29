pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                script {
                    def message = "Hello Jenkins File Hieber in VSC via VAR"
                    echo message
                }
            }
        }

        stage('Stage2') {
            steps {
                echo "Stage 2"
            }
        }

        stage('Stage3') {
            steps {
                echo "Stage 3"
                sh 'printenv'
            }
        }
    }
}

pipeline {
    agent any
    environment {
        STAGECHECK = "true"
    }
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
            when { expression { env.STAGECHECK == "false" } }
            steps {
                echo "Stage 3"
                sh 'printenv'
            }
        }
    }
}

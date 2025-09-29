pipeline {    
    agent any

    environment  {
        execute_state2 = false
    }
    

    stages {
        stage('Stage 1') {
            steps {
                echo 'Stage 1'
            }
        }
        stage('Stage 2') {
            when {
                environment name: 'execute_state2', value: 'true'
            }
            steps {
                echo 'Stage 2'
            }
        }
        stage('Stage 3') {
            steps {
                echo 'Stage 3'
                sh 'printenv123'   
            }
        }
    }

    post {
        success {
            echo "Pipeline was successful"
        }
        failure {
            echo "Something really bad happened, DO SOMETHING!!!"
        }
    }
}

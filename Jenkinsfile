pipeline {
    agent any

    stages {
        stage('Run') {
            steps {
                script {
                    echo 'Starting task...'
                    def myVar = 'hello'          
                    echo "Value is: ${myVar}"
                }
            }
        }
    }

    post {
        always {
            echo 'This always runs, pass or fail.'
        }
        success {
            echo ' Pipeline succeeded.'
        }
        failure {
            echo ' Pipeline failed — check logs above for the error.'
        }
    }
}

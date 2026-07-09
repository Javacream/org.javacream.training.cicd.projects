pipeline {
    agent any

    environment {
        Maus = 7
    }

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
                echo Maus
            }
        }
    }
    post {
        success {
            echo 'gut'
        }
        failure {
            echo 'schlecht'
        }
    }
}

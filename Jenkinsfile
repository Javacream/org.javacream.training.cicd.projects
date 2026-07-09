pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                ech 'Hello World'
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

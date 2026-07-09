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
/*                if (Maus % 2 ==0) {
                    echo 'gerade'
                } else {
                    echo 'ungerade'
                }
 */           
            }
        }
    }
    post {
        success {
            echo 'lief gut'
        }
        failure {
            echo 'lief schlecht'
        }
    }
}

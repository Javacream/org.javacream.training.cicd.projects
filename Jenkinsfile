pipeline {
    agent any

    stages {
        stage('Hello') {
            message = "Hello stage"
            steps {
                echo 'Hello Jenkins File'
                echo 'Hello me hearties!'
                echo '${message}'
            }
        }
        stage('Board') {
            steps {
                echo 'Release the parrots!'
                echo 'Test!?'
            }
        }
    }
}

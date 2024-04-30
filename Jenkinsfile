pipeline {
    agent {docker {image 'python'}}

    stages {
        stage('Hello') {
            steps {
                sh 'python simple.py'
            }
        }
    }
}
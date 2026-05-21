pipeline {
    agent none

    stages {
        stage('Hello Python') {
            agent {
                label 'python'
            }
            steps {
                sh 'python -V'
            }
        }
        stage('Hello Java') {
            agent {
                label 'java'
            }
            steps {
                sh 'mvn -version'
            }
        }
        stage('Wrong Python') {
            agent {
                label 'java'
            }
            steps {
                sh 'python -V'
            }
        }
    }
}

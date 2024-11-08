pipeline {
    agent {label "agent1"}

    stages {
        stage('Check docker') {
            steps {
                sh 'docker --version'
            }
        }
    }
}
pipeline {
    agent {label "docker"}

    stages {
        stage('Check docker') {
            steps {
                sh 'docker --version'
            }
        }
    }
}
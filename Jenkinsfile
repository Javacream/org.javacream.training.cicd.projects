pipeline {
    agent {label "docker"}

    stages {
        stage('Check docker') {
            steps {
                sh 'docker --version'
            }
        }
        stage('Check Maven Build Container') {
            steps {
                sh 'docker run --rm maven mvn -version'
            }
        }
    }
}
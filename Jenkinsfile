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
        stage('Developer Build') {
            steps {
                /* Funktioniert so nicht. Es fehlt das Mounten des Workspaces!

                sh 'docker run --rm maven mvn install'

                */
                sh 'ls'
            }
        }

    }
}
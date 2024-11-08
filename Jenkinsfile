pipeline {
    agent {docker {image "maven"}}

    stages {
        stage('Developer Build') {
            steps {
                sh 'mvn -f org.javacream.training.rest.people.server install ' 
                sh 'ls org.javacream.training.rest.people.server/target'
            }
        }

    }
}
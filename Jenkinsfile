pipeline {
    agent none
    stages {
        stage('Developer Build') {
            agent {docker {image "maven"}}
            steps {
                sh 'mvn -f org.javacream.training.rest.people.server install ' 
                sh 'ls org.javacream.training.rest.people.server/target'
            }
        }
        stage('Integration Tests') {
            agent {docker {image "openjdk:8-alpine"}}

            steps {
                    sh 'java -jar org.javacream.training.rest.people.server-1.0.jar'
                    sh 'wget -O people.json localhost:8080/people'
                    sh 'cat people.json'
            }
        }

    }
}
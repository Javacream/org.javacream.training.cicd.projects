pipeline {
    agent none
    stages {
        stage('Developer Build') {
            agent {docker {image "maven"}}
            steps {
                sh 'mvn -f org.javacream.training.rest.people.server install ' 
                sh 'ls org.javacream.training.rest.people.server/target'
                stash includes: "target/*.jar", name: "jars" 
            }
        }
        stage('Integration Tests') {

            agent {docker {image "openjdk:8-alpine"}}

            steps {
                    unstash "jars"
                    sh 'java -jar org.javacream.training.rest.people.server/target/org.javacream.training.rest.people.server-1.0.jar &'
                    sh 'sleep 3'
                    sh 'wget -O people.json http://localhost:8080/people'
                    sh 'cat people.json'
                    sh 'killall java'
            }
        }

    }
}
pipeline {
    agent none
    stages {
        stage('Developer Build') {
            agent {docker {image "maven"}}
            steps {
                sh 'mvn -f org.javacream.training.rest.people.server install ' 
                sh 'ls org.javacream.training.rest.people.server/target'
                stash includes: "org.javacream.training.rest.people.server/target/*.jar", name: "jars" 
            }
        }
        stage('Image Build'){
            agent {label 'docker'}
            steps{
               unstash "jars"
               sh 'docker build -t javacream/app:1.0 .'
            }

        }
        stage('Integration Tests') {

            agent {label 'docker'}

            steps {
                    sh 'docker run -d --rm --name sawitzki_app -p 8090:8080 javacream/app:1.0'
                    /*
                    sh 'sleep 10'
                    sh 'curl http://10.160.1.128:8090/people > people.json '
                    sh 'cat people.json'
                    */
                    sh 'docker stop sawitzki_app'
            }
        }

    }
}
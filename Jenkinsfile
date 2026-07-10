pipeline{
    agent none
    stages{
        stage('Developer Build'){
           agent {
                docker {
                    label 'docker'
                    image 'maven'
                    }
            }

            steps{
                sh 'ls'
                sh 'mvn install'
                sh 'ls target'
            }
        }
    }


}

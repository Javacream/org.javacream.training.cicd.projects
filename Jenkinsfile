pipeline{
    agent {docker {image 'maven'}}
    stages{
        stage('Developer Build'){
            steps{
                sh 'mvn install'
            }
        }
    }


}
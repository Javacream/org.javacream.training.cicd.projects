pipeline{
    agent {docker {image 'maven'}}
    stages{
        stage('Developer Build'){
            steps{
                echo 'starting developer build'
                sh 'ls'
                sh 'mvn deploy'
            }
        }
    }


}
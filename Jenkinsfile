pipeline{
    agent {docker {image 'mvn'}}
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
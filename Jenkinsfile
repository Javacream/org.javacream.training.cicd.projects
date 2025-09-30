pipeline{
    agent {docker {image 'javacream/maven:2.0'}}
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
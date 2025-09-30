pipeline{
    agent {docker {image 'javacream/maven'}}
    stages{
        stage('Developer Build'){
            steps{
                echo 'staring developer build'
                sh 'ls'
                sh 'mvn deploy'
            }
        }
    }


}
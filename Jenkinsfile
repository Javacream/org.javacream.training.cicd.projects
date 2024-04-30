pipeline{
    agent {docker {image 'javacream/maven'}}
    stages{
        stage('Developer Build'){
            steps{
                sh 'mvn deploy'
            }
        }
    }


}
pipeline {
  agent any

  environment{
    MESSAGE_GLOBAL = "Global Message Schwabe"
  }

  stages {
    stage('Hello') {
      environment{
        MESSAGE = "Hello Schwabe editing from Message VSC"
      }

      steps{
        echo "Stage Message: ${MESSAGE}"
        echo "Global Message: ${MESSAGE_GLOBAL}"
      }
    }

    stage('Main Stage') {
      when{
        expression{
          return !MESSAGE_GLOBAL.contains('Schwabe');
        }
      }
      steps{
        echo 'Hello in Main Stage'
        sh 'printenv'
      }
    }

    stage('Parallel Stages') {
      parallel {
        stage('Stage A'){
          steps{
            echo 'Stage A test'
          }
        }

        stage('Stage B'){
          steps{
            echo 'Stage B test'
          }
        }

        stage('Stage C'){
          stages{
            stage('Stage C1'){
              steps{
                echo 'Stage C1 test'
              }
            }
            stage('Stage C2'){
              steps{
                echo 'Stage C2 test'
              }
            }
          }
        }
      }
    }

    stage('Goodbye') {
      environment{
        MESSAGE_END = "Hello Schwabe editing from Message VSC"
      }
      when{
        expression{
          return MESSAGE_GLOBAL.contains('Schwabe');
        }
      }
      steps{
        echo "Global Message: ${MESSAGE_GLOBAL}"
        echo "End Message: ${MESSAGE_END}"
      }
    }
  }
}

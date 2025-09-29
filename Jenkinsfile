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
        var localMessage = "local message"
        echo 'Stage Message: ${MESSAGE}'
        echo 'Global Message: ${MESSAGE_GLOBAL}'
        sh 'printenv'
      }
    }

    stage('Optional Stage') {
      steps{
        sh 'printenv'
      }
    }

    stage('Goodbye') {
      messageEnd = "Hello Schwabe editing from Message VSC"

      steps{
        echo '${MESSAGE_GLOBAL}'
        echo '${messageEnd}'
      }
    }
  }
}

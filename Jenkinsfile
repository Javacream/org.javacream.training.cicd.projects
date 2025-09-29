pipeline {
  agent any

  messageGlobal = "Global Message Schwabe"

  stages {
    message = "Hello Schwabe editing from Message VSC"

    stage('Hello') {
      steps{
        echo '${message}'
        echo 'Global Message: ${messageGlobal}'
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
        echo '${messageGlobal}'
        echo '${messageEnd}'
      }
    }
  }
}

pipeline {
  agent any
  environment {
    messageGlobal = "Global Message"
  }

  stages {
    environment {
      message = "Hello Schwabe editing from Message VSC"
    }
    stage('Hello') {
      steps{
        echo '${message}'
        echo 'Global Message: ${messageGlobal}'
      }
    }

    stage('Goodbye') {
      environment {
        messageEnd = "Hello Schwabe editing from Message VSC"
      }
      steps{
        echo '${messageGlobal}'
        echo '${messageEnd}'
      }
    }
  }
}

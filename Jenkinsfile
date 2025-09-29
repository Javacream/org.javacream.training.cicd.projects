pipeline {
  agent any
  messageGlobal = "Global Message"

  stages {
    message = "Hello Schwabe editing from Message VSC"
    stage('Hello') {
      steps{
        echo '${message}'
        echo '${messageGlobal}'
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

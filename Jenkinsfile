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
        def localMessage = 'local message'
        echo 'Local Message: ${localMessage}'
        echo 'Stage Message: ${MESSAGE}'
        echo 'Global Message: ${MESSAGE_GLOBAL}'
      }
    }

    stage('Main Stage') {
      steps{
        echo 'Hello in Main Stage'
        sh 'printenv'
      }
    }

    stage('Goodbye') {
      environment{
        MESSAGE_END = "Hello Schwabe editing from Message VSC"
      }

      steps{
        echo '${MESSAGE_GLOBAL}'
        echo '${MESSAGE_END}'
      }
    }
  }
}

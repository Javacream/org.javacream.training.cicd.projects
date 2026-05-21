pipeline {
    agent none
    environment { 
        CC = 'clang'
        VERSION = "1.0"
    }
    stages {
        stage('Parallel Stage') {
            parallel {
                stage('Build') {
                   agent {
                        label 'python'
                    }
                    steps {
                        echo "Version ${VERSION}"
                        sh 'python -V'
                    }
                }
                stage('Test') {
                    agent {
                        label 'java'
                    }
                    steps {
                        sh 'mvn -version'
                    }
                }
          }
    }
}
post {
    success {
        echo 'Pipeline erfolgreich'
    }
    failure {
        echo 'Pipeline fehlgeschlagen'
    }
}
}

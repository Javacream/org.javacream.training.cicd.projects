pipeline {
    agent any

    environment {

        runTests = 'false' // bool flag to control stage 2
    }


    stages {

        stage('Build') {

            steps {
                script
                {
                    echo 'Starting Stage 1: Build ${REPO_NAME}'
                    
                    // Set condition to execute Stage 2
                    runTests = 'true'
                }
            }            
        }

        stage('Test') {
            when {
                expression
                {
                    return env.runTests == 'true'
                }
            }
                        
            steps {
                echo 'Stage 1 was successful - ok!'
                echo 'Starting Stage 2: Test'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Starting Stage 3: Deploying Software :)'
            }
        }
    }

    post
    {
        always
        {
            echo 'Pipeline completed'
        }
        success
        {
            echo '=> success!'
        }
        failure
        {
            echo '=> failed!'
        }
    }
}

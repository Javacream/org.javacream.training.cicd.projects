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
                    //echo "Starting Stage 1: Build ${REPO_NAME}"
                    
                    // Set condition to execute Stage 2
                    env.runTests = 'true'
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
            parallel
            {
                echo 'Starting Stage 3: Deploying Software :)'

                stage ('Deplay Windows')
                {
                    steps 
                    {
                        echo "Windows done!"
                    }
                }
                stage ('Deploy Linux')
                {
                    steps 
                    {
                        echo "Linux done!"
                    }
                }
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

pipeline {
    agent any

    environment
    {
        RUN_TESTS = 'false' // bool flag to control stage 2
    }

    stages {
        stage('Build') {
            steps
            {
                echo "Starting Stage 1..."
                echo "Test run: ${RUN_TESTS}"
                RUN_TESTS = 'true'
                echo "Test run: ${RUN_TESTS}"
            }            
        }

        stage('Test') {                       
            steps
            {
                echo 'Stage 1 was successful - ok!'
                echo 'Starting Stage 2: Test'
            }
        }

        stage('Deploy') {
            parallel
            {
                stage ('Deploy Windows')
                {
                    steps 
                    {
                        echo 'Starting Stage 3.1: Deploying Software :)'
                        echo "Windows done!"
                    }
                }
                stage ('Deploy Linux')
                {
                    steps 
                    {
                        echo 'Starting Stage 3.2: Deploying Software :)'
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

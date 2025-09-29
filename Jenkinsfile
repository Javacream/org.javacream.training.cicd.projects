pipeline {
    agent any

    environment
    {
        RUN_TESTS = null // bool flag to control stage 2
    }

    stages {
        stage('Build') {
            steps
            {
                script {
                    echo "Starting Stage 1..."
                    echo "Test run: ${env.RUN_TESTS}"
                    env.RUN_TESTS = 'true'
                    echo "Test run: ${env.RUN_TESTS}"
                }
            }            
        }

        stage('Test') {                       
            steps
            {
                script {
                    if (env.RUN_TESTS.toBoolean())
                    {
                        echo 'Stage 1 was successful - ok!'
                        echo 'Starting Stage 2: Test'
                    }
                    else
                    {
                        echo 'Stage 2 failed!'
                        echo 'No Tests executed...'
                    }
                }
            }
        }

        stage('Deploy') {

            when { expression { return env.RUN_TESTS.toBoolean() }}

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

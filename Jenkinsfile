pipeline{
    agent any
    stages{
        stage('Verify Branch')
        steps{
            echo "$ GIT_BRANCH"
        }
    }
    stage('DOCKER BUILD')
    {
        steps
        {
            pwsh(Script: 'docker images -a')
            pwsh
            (Script: """
                    cd azure-vote/
                    docker images -a
                    docker build -t jenkins-pipeline .
                    docker images -a
                    cd ..
        """)

        }
    }
}
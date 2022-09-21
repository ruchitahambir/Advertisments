/*pipeline{
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
}*/

pipeline {
          agent {
                   docker {
                             image 'node:6-alpine'
                             args '-p 3000:3000'
                          }


                }
          /*environment {
                        CI = 'true'
                      }*/
          stages {
                     stage('Build') {
                         steps {
                                 sh 'npm install'
                               }
                      }
                  
                      /*stage('Test') {
                         steps {
                                 sh './jenkins/scripts/test.sh'
                               }
                      }
                      stage('Deliver') {
                         steps {
                                 sh './jenkins/scripts/deliver.sh'
                                 input message: 'Finished using the web site? (click "Proceed" to continue)'
                                 sh './jenkins/scripts/kill.sh'
                               }
                      }*/
                 }

}
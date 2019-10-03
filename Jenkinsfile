pipeline {
    agent any 
    environment
    {
            CI = 'true'
    }
    stages {
        stage ('Install') {
        steps{
            bat 'npm install'
        }
        }
    }
}

                                   
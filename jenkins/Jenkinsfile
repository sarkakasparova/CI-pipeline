pipeline {
    agent {
        docker {
            image 'node:8-alpine'
            args '-p 3000:3000'
        }
    }
	environment { 
        CI = 'true'
    }
    stages {
        stage('Install') {
            steps {
                sh 'npm install'
            }
        }
		stage('Test') {
            steps {
                sh 'npm run test'
            }
        }
		stage('Build') {
			steps {
				sh 'npm rebuild node-sass'
				sh 'npm run build'
			}
		}
    }
}

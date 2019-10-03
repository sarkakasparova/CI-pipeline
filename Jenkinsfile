pipeline {
  agent any
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
        sh 'npm run build'
      }
    }
    stage('Deploy') {
      when {
        expression {"$env.GIT_BRANCH" == "origin/master"}
      }
      steps {
        sh './node_modules/.bin/firebase deploy --token=$FIREBASE_DEPLOY_TOKEN'
      }
    }
  }
}
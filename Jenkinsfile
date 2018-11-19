pipeline {
  agent any
  stages {
    stage('Checkout') {
      agent any
      environment {
        SAFE_BRANCH_NAME = '${BRANCH_NAME}'
      }
      steps {
        deleteDir()
        echo sh(returnStdout: true, script: 'env')
        sh '$BRANCH_NAME | sed \'/\\./\\_/g\''
      }
    }
    stage('Build') {
      steps {
        echo sh(returnStdout: true, script: 'env')
        echo 'Build'
      }
    }
    stage('Prune') {
      steps {
        echo 'prune'
      }
    }
    stage('Build Image') {
      steps {
        echo 'Build Image'
      }
    }
    stage('Deploy') {
      steps {
        echo 'DEPLOY JENKINS'
      }
    }
  }
}
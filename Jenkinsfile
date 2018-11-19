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
      }
    }
    stage('Build') {
      steps {
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
  environment {
    SAFE_BRANCH_NAME = TEST_${BRANCH_NAME}${BUILD_ID}
  }
}
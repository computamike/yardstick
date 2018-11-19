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
        SAFE_BRANCH_NAME = sh(returnStdout: true, script:'BRANCH_NAME.replace(".", "_").replaceAll('/', '_').replaceAll('-', '_')')
        echo sh(returnStdout: true, script: 'env')
    
        
        
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

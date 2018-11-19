pipeline {
  agent {
    node {
      label 'master'
    }

  }
  stages {
    stage('Checkout') {
      steps {
        slackSend(message: ':building_construction: Started Build: YARDSTICK ${env.BRANCH_NAME} #${env.BUILD_NUMBER}', botUser: true, channel: '#jenkins', color: 'warn')
        deleteDir()
        echo sh(returnStdout: true, script: 'env')
        // SAFE_BRANCH_NAME = BRANCH_NAME.replace(".", "_").replaceAll('/', '_').replaceAll('-', '_')
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
}

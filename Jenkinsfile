pipeline {
  agent {
    node {
      label 'master'
    }

  }
  stages {
    stage('Checkout') {
      steps {
        deleteDir()
        echo sh(returnStdout: true, script: 'env')
        sh '${sh(returnStdout: true, script: "SAFE_BRANCH_NAME=\'my value\'")}'
        echo '${sh(returnStdout: true, script: \'env\')}'
        sh(returnStdout: true, script: 'SAFE_BRANCH_NAME = ${BRANCH_NAME//./_}')
        sh '"SAFE_BRANCH_NAME = ${SAFE_BRANCH_NAME////_}"'
        sh 'SAFE_BRANCH_NAME = ${SAFE_BRANCH_NAME//-/_}'
        sh 'mysql -u root -p1234 -e "DROP DATABASE IF EXISTS highstreet_${SAFE_BRANCH_NAME}_${BUILD_NUMBER}"'
        slackSend(message: ':building_construction: Started Build: YARDSTICK ${env.BRANCH_NAME} #${env.BUILD_NUMBER}', botUser: true, channel: '#jenkins', color: 'warn')
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
    SAFE_BRANCH_NAME = 'test'
  }
}
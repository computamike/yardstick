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
        sh '${sh(returnStdout: true, script: "SAFE_BRANCH_NAME=\\"my value\\"")}'
        echo '${sh(returnStdout: true, script: \'env\')}'
        sh 'export AWESOME_FILE=$SAFE_BRANCH_NAME/the_file'
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
    SAFE_BRANCH_NAME = 'test'
  }
}
pipeline {
  agent {
    node {
      label 'master'
    }

  }
  stages {
    stage('Checkout') {
      steps {
        echo 'test'
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
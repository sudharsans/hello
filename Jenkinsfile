pipeline {
  agent any
  stages {
    stage('Build') {
      parallel {
        stage('Build') {
          steps {
            echo 'test'
          }
        }
        stage('Build1') {
          steps {
            echo 'Build1'
          }
        }
        stage('Build2') {
          steps {
            echo 'Build2'
          }
        }
      }
    }
    stage('Test') {
      steps {
        echo 'testing'
      }
    }
    stage('Done') {
      steps {
        echo 'build done'
      }
    }
  }
}
pipeline {
  agent any
  stages {
      stage('Build') {

      parallel {
        stage('Build') {
          steps {
            echo 'test'
            checkout changelog: true, poll: true, scm: [$class: 'GitSCM', branches: [[name: '*/develop']], doGenerateSubmoduleConfigurations: false, extensions: [[$class: 'PreBuildMerge', options: [fastForwardMode: 'FF', mergeRemote: 'https://github.com/sudharsans/hello.git', mergeTarget: 'master']]], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/sudharsans/hello.git']]]
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
      parallel {
        stage('Test') {
          steps {
            echo 'testing'
          }
        }
        stage('another test') {
          steps {
            sh 'echo "another tets"'
          }
        }
      }
    }
    stage('Done') {
      steps {
        echo 'build done'
      }
    }
    stage('test') {
      steps {
        sh 'echo "test"'
      }
    }
  }
}

pipeline {
  agent any
  stages {
    stage('Build') {
      parallel {
        stage('Build') {
          steps {
            echo 'test'
            checkout(changelog: true, poll: true, scm: [$class: 'GitSCM', branches: [[name: '*/develop']], doGenerateSubmoduleConfigurations: false, extensions: [[$class: 'PreBuildMerge', options: [fastForwardMode: 'FF', mergeRemote: 'origin', mergeTarget: 'master']]], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'github', url: 'https://github.com/sudharsans/hello.git']]])
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
    stage('Push') {
      steps {
        sh '''git config --global user.email "sudharsan.sivasankaran@gmail.com"
git config --global user.name "Sudharsan"
git tag -a some_tag123 -m \'Jenkins\'
git push master --tags'''
      }
    }
  }
}
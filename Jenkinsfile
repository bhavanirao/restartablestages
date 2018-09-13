pipeline {
  agent any
  stages {
    stage('stage1:build') {
      steps {
        echo 'This shouldn\'t show up on second run'
      }
    }
    stage('stage2:test') {
      steps {
        script {
          if (currentBuild.getNumber() % 2 == 1) {
            error("Odd numbered build, failing")
          } else {
            echo "Even numbered build, success"
          }
        }

      }
    }
    stage('stage3:deploy to prod') {
      steps {
        echo 'Now we\'re deployed successfuly'
      }
    }
  }
}
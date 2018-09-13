pipeline {
  agent any
  stages {
    stage('step1:build') {
      steps {
        echo 'This shouldn\'t show up on second run'
      }
    }
    stage('step2:test') {
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
    stage('step3:deploy to prod') {
      steps {
        echo 'Now we\'re post-restart'
      }
    }
  }
}
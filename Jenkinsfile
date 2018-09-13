pipeline {
  agent any
  stages {
    stage('skip-on-restart') {
      steps {
        echo 'This shouldn\'t show up on second run'
      }
    }
    stage('restart') {
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
    stage('post-restart') {
      steps {
        echo 'Now we\'re post-restart'
      }
    }
  }
}
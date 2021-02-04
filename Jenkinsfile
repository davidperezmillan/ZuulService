pipeline {
  agent any
  stages {
    stage('error') {
      steps {
        sh 'echo"${name}"'
      }
    }

  }
  environment {
    name = 'davidperez01/zuulservice'
  }
}
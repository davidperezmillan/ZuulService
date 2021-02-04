pipeline {
  agent any
  stages {
    stage('error') {
      steps {
        sh 'print ${env.name}'
      }
    }

  }
  environment {
    name = 'davidperez01/zuulservice'
  }
}
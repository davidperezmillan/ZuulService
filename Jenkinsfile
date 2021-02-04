pipeline {
  agent any
  environment {
    name = 'davidperez01/zuulservice'
  }
  stages {
    stage('Clean') {
      agent any
      steps {
        echo 'Clean mvn'
        sh 'mvn clean -DskipTests=true'
      }
    }

    stage('Test') {
      agent any
      environment {
        registry = $env.name
        registryCredential = 'dockerhub'
      }
      steps {
        echo 'Test Project'
        sh 'mvn test'
      }
    }

    stage('Build & Docker') {
      steps {
        echo 'mvn Build'
        sh 'mvn install -DskipTests=true'
        echo 'Docker Imagen'
        sh 'docker image build -t davidperez01/zuulservice .'
      }
    }

    stage('Docker Register') {
      steps {
        echo 'Register Docker'
        echo 'Nombre del proyecto: $name'
      }
    }

  }
}

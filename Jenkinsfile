pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh './mvnw package'
      }
    }

    stage('2') {
      steps {
        echo 'hello'
      }
    }

    stage('3') {
      steps {
        echo 'world'
      }
    }
  }
}
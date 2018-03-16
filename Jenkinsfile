pipeline {
  agent any
  stages {
    stage('Unit Test') {
      steps {
        sh 'mvn clean test'
      }
    }
    stage('Deploy Local') {
      steps {
        sh 'mvn deploy -P standalone'
      }
    }
  }
}
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
    stage('Deploy CloudHub') {
      environment {
        ANYPOINT_CREDENTIALS = credentials('anypoint.credentials')
      }
      steps {
        sh 'mvn deploy -P cloudhub -Danypoint.username=${MYVARNAME_USR} -Danypoint.password=${MYVARNAME_PSW}'
      }
    }
  }
}
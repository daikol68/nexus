pipeline {
  agent any
  environment {
    branch = 'master'
    scmUrl = 'https://github.com/daikol68/nexus'
  }
  stages {
    stage('checkout git') {
      steps {
        git branch: branch, credentialsId: 'GitCredentials', url: scmUrl
      }
    }

    stage('build') {
      steps {
        sh 'mvn clean package'
      }
    }

    stage('deploy'){
      steps {
        sh 'mvn deploy'
      }
    }
  }
}
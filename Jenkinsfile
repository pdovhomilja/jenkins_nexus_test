pipeline {
  agent any
  stages {
    stage('Github') {
      steps {
        git(url: 'https://github.com/pdovhomilja/jenkins_nexus_test', branch: 'main')
      }
    }

    stage('Test NodeJS') {
      steps {
        sh 'sh node --version'
      }
    }

  }
}
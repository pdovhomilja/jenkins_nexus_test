pipeline {
  agent any
  stages {
    stage('Github') {
      steps {
        git(url: 'https://github.com/pdovhomilja/jenkins_nexus_test', branch: 'main')
      }
    }

    stage('NodeJS') {
      steps {
        nodejs('18.2') {
          sh 'node -v'
        }

      }
    }

  }
}
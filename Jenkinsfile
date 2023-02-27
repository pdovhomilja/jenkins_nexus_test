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
        nodejs('NodeJS-18') {
          sh 'node -v'
        }

      }
    }

    stage('Build') {
      steps {
        sh 'npm install && npm run build'
      }
    }

  }
}
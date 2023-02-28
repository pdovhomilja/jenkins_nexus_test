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
          sh 'npm install && npm run build'
        }

      }
    }

    stage('Log') {
      steps {
        sh 'ls -la'
      }
    }

    stage('build Docker') {
      steps {
        sh 'docker build -t nexus.faircredit.cz:8082/jenkins-nexus-test:latest .'
        sh 'docker push nexus.faircredit.cz:8082/jenkins-nexus-test:latest'
      }
    }

  }
}
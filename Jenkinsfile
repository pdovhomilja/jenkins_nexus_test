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
    
    stage('Initialize'){
      steps{
        def dockerHome = tool 'myDocker'
        env.PATH = "${dockerHome}/bin:${env.PATH}"
      }
    }

    stage('build Docker') {
      steps {
        sh 'docker build -f Dockerfile .'
      }
    }

  }
}

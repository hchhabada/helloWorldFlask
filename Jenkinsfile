pipeline {
  agent { docker { image 'python:3.7.2' } }
  stages {
    stage('Initialize') {
      steps {
          sh 'def dockerHome = tool "myDocker"'
           sh 'env.PATH = "${dockerHome}/bin:${env.PATH}"'
       }
    }
    stage('build') {
      steps {
        sh 'pip install -r requirements.txt'
      }
    }
    stage('test') {
      steps {
        sh 'python test.py'
      }   
    }
  }
}

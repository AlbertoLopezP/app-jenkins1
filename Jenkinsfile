pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'BUILD'
		    sh 'docker build -t app .'
      }
    }
    stage('Test') {
      steps {
        echo 'TEST'
      }
    }
	stage('Deploy') {
      steps {
        echo 'DEPLOY'
      }
    }
  }
}
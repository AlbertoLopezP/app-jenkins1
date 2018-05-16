pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'docker build -t app .'
      }
    }
    stage('Test') {
      steps {
        echo 'TEST'
		sh '/bin/nc -vz localhost 22'
	
      }
    }
	stage('Push Registry') {
      steps {
        echo 'DEPLOY'
		sh 'docker tag app:test app:stable'
		sh 'docker push aremox/app:stable'
      }
    }
  }
}

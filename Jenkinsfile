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
		sh 'docker run -it app'
		sh '/bin/nc -vz localhost 80'
		sh 'docker stop app'
      }
    }
	stage('Push Registry') {
      steps {
        echo 'DEPLOY'
		sh 'docker tag app aremox/app:stable'
		sh 'docker push aremox/app:stable'
      }
    }
  }
}

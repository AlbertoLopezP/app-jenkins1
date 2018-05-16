pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'docker build -t app:test .'
      }
    }
    stage('Test') {
      steps {
        echo 'TEST'
		sh 'docker run -d -p 80:80 --name app --rm app:test'
		sh '/bin/nc -vz localhost 80'
		sh 'docker stop app'
      }
    }
	stage('Push Registry') {
      steps {
		withCredentials([usernamePassword(credentialsId: 'aremox_dockerhub', passwordVariable: 'Password', usernameVariable: 'Usuario')]) {		echo 'DEPLOY'
		sh 'docker tag app:test aremox/app:stable'
		sh 'docker login --password $Password --username $Usuario'
		sh 'docker push aremox/app:stable'
		}
      }
    }
  }
}

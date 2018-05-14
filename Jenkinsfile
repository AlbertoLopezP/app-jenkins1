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
      }
    }
	stage('Deploy') {
      steps {
        echo 'DEPLOY'
      }
    }
	post {
		always(dir){
			cleanWS
			echo "Esto siempre sale por pantalla"
		}
	}
  }
}

pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'BUILD'
		echo ''
      }
    }
	post {
		always{
			echo "Esto siempre sale por pantalla"
		}
		failure {
			echo "Fallo"
		}
		success {
			echo "Ha salido bien"
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

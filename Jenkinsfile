pipeline {
	agent any
	stages{


		stage('Build') {	
			steps {
				echo "Build"
			}
		}


		stage('Test') {
			steps {
				echo "Test"
			}
		}


		stage('Integreation Test') {
			steps {
				echo "Integreation Test"
			}
		}
}
    post {
		always {
		echo 'i am good'		
	}
		success {
		echo 'i ran when success'		
	}
		failure {
		echo 'i ran when success'		
	}		
	
	}
}
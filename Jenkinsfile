pipeline {
	agent any

	environement{

		dockerHome= tool 'myDocker'
		mavenHome= tool 'myMaven'
		PATH= '$dockerHome/bin:$mavenHome/bin:$PATH'
	}

	stages{


		stage('Build') {	
			steps {
				echo "Build"
				sh 'mvn --version'
				echo "Build"
				sh 'docker version'
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
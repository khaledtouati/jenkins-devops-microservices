pipeline {
	agent any

	environment{

		dockerHome= tool 'myDocker'
		mavenHome= tool 'myMaven'
		PATH= '$dockerHome/bin:$mavenHome/bin:$PATH'
	}

	stages{


		stage('Checkout') {	
			steps {
				echo "Build"
				sh 'mvn --version'
				echo "Build"
				sh 'docker version'
			}
		}

		stage('Compile') {
			steps {
				echo "TeBuildst"
				sh "mvn clean compile"
			}
		}

		stage('Test') {
			steps {
				echo "Test"
				sh "mvn test"
			}
		}


		stage('Integreation Test') {
			steps {
				echo "Integreation Test"
				sh "mvn failsafe:integration-test failsafe:verify"
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
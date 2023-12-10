pipeline {
	agent any

	environment{

		dockerHome= tool 'myDocker'
 		PATH= '$dockerHome/bin:$PATH'
	}

	stages{


		stage('Checkout') {	
			steps {
 
				echo "Build"
				sh 'docker version'
			}
		}
 
		stage('Test') {
			steps {
				echo "Test"
				 
			}
		}


 


		stage('build image') {
			steps {
				echo "build image"
			//	docker build -t khaledkhaled/currency:$env.BUILD_TAG 
				script{
					dockerimage =	docker.build("khaledkhaled/currency:${env.BUILD_TAG}")

				}

				 
			}
		}

		stage('Push image') {
			steps {
				echo "build image"
			  	script{
					docker.withRegistry('','dockerhub') {
					dockerimage.Push();
					dockerimage.Push('latest');
				}	}
				 
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
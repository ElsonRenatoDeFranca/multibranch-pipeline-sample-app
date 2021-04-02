pipeline{
   
   	agent any
   
   	stages{
     	
		stage('Checkout code') {
			steps {
				checkout scm
			}
		}
		stage('Build'){
			steps{
				echo 'Compiling the application....'
			}
     	}
		stage('Test'){
			steps{
				echo 'Testing the application...'
			}
		}

		stage('Deploy'){
			steps{
				echo 'Deploying the application....'
			}
		}
     }
}

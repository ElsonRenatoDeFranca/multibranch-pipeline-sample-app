pipeline{
   
   	agent any
   
   	stages{
     	
		stage('Checkout code') {
			steps {
				checkout scm
			}
		}
		stage('Build'){
			tools{
			 gradle 'gradle6'
			}
			steps{
				echo 'Compiling the application....'
				sh 'gradle clean build'
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

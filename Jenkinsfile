pipeline{
   
   	agent any
   
   	stages{
     	
		stage('Build'){
			steps{
				echo 'Compiling the application....'
				withGradle(){
				  sh './gradlew -v'
				  sh './gradlew clean build'
				}

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

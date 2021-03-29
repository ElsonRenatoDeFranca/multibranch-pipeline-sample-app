pipeline{
   
   	agent any
   
   	stages{
     	
		stage('Build'){
			steps{
				echo 'Compiling the application...'
				gradlew('clean', 'classes')
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

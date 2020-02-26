pipeline{
	agent any
	stages{
		stage("Initial stage"){
			steps{

				withMaven("3_6_3"){
					sh 'mvn clean'
				}
			}
		}
		
		stage("Compile stage"){
			steps{

				withMaven("3_6_3"){
					sh 'mvn compile'
				}
			}
		}
		
		stage("Test stage"){
			steps{

				input ("Do you want to proceed")
				withMaven("3_6_3"){
					sh 'mvn test'
				}
			}
		}
		
		stage("Deployment stage"){
			steps{

				withMaven("3_6_3"){
					sh 'mvn deploy'
				}
			}
		}
	}
}


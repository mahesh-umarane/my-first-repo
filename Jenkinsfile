pipeline{
	agent any
	stages{
		stage("Initial stage"){
			steps{
				echo "It is Initial stage"
				withMaven("3_6_3"){
					sh "mvn clean"
				}
			}
		}
		
		stage("Compile stage"){
			steps{
				echo "It is Compile stage"
				withMaven("3_6_3"){
					sh "mvn compile"
				}
			}
		}
		
		stage("Test stage"){
			steps{
				echo "It is Test stage"
				input ("Do you want to proceed")
				withMaven("3_6_3"){
					sh "mvn test"
				}
			}
		}
		
		stage("Deployment stage"){
			steps{
				echo "It is Deployment stage"
				withMaven("3_6_3"){
					sh "mvn deploy"
				}
			}
		}
	}
}


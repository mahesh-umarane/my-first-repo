node {
   def mvnHome
   stage('First Stage') { // for display purposes
      // Get some code from a GitHub repository
      git 'https://github.com/mahesh-umarane/my-first-repo'
      // Get the Maven tool.
      // ** NOTE: This 'M3' Maven tool must be configured
      // **       in the global configuration.   
   }
   stage('Second stage') {
      mvnHome = tool 'M2_HOME'
      // Run the maven build
      withEnv(["MVN_HOME=$mvnHome"]) {
         if (isUnix()) {
            sh '"$MVN_HOME/bin/mvn" -Dmaven.test.failure.ignore clean install compile package'
         } else {
            bat(/"%MVN_HOME%\bin\mvn" -Dmaven.test.failure.ignore clean package/)
         }
      }
   }
   stage('deploy') {
      deploy adapters: [tomcat9(credentialsId: '50770e3a-2a06-41ff-8c87-1c9a6bd83ce5', path: '', url: 'http://192.168.43.167:8080/')], contextPath: null, war: '**/*.war'
   }
   stage('Results') {
      echo "Executed successfully"
   }
}

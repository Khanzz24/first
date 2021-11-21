node{
    def mvnHome
 
   stage('SetEnv') { 
      git 'https://github.com/Khanzz24/first.git'
      mvnHome = tool 'MAVEN_HOME'
	   
   }
   
   stage('CompileandPackage') {
      withEnv(["MVN_HOME=$mvnHome"]) {
            bat(/"%MVN_HOME%\bin\mvn" -Dmaven.test.failure.ignore clean compile/)
         }
      
   }
   stage('Snyk'){
        snykSecurity failOnIssues: false, organisation: '00b78d8c-3cb5-48c4-9c4f-d4ab36ed674e', snykInstallation: 'Snyknew', snykTokenId: 'Snykey2'
       
   }

}

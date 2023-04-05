pipeline {
  agent any
  tools {
  maven 'maven'
  }
    stages {
	  
	stage ('Build')  {
	    steps {
        dir('app'){
            sh "mvn package"
          }
        }    
   }
   
  stage ('SonarQube Analysis') {
    steps {
      withSonarQubeEnv('sonar-cred') {
	      {
                sh 'mvn verify org.sonarsource.scanner.maven:sonar-maven-plugin:sonar -Dsonar.projectKey=ankit123
        }
    }
    }
 }
}	    

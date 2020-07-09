/*@Library('shlib')_
pipeline {
	 tools {
        maven "mvn"   
    }   
    agent any
  
    stages {
	    stage('clonestage'){
		    steps{
		   //sh 'rm -rf assessmentdocker' 
	       // sh 'git clone https://github.com/SumaVarshitha/assessmentdocker.git'
		    clonerepo()
		    }}
		 
        stage('build') {
            
		 
		steps {
	           dockerbuild()
                }
			
            
	    }
        
        stage('SonarQube Analysis'){
		
		// environment{
               //sonarscanner = tool 'sonars'
                  // }
            steps{
              // withSonarQubeEnv('sonar'){
                   // sh '${sonarscanner}/bin/sonar-scanner -Dproject.settings=./sonar-project.properties'
		       //sh "${scannerHome}/bin/sonar-scanner"
              // sh 'mvn sonar:sonar'
		    sonarqube()
	       }
            }
       // }

    
        
      stage("Quality Gate") {
            steps {
             // timeout(time: 3, unit: 'MINUTES') {
               // waitForQualityGate abortPipeline: true
		    qualitygate()
              }
            }
        //}
    }
}
*/
Pipeline {
	 tools {
        maven "mymaven"   
    }   
    agent any
  
    stages {
	    //stage('remove'){
	   // stages {
	    stage('clonestage'){
		    steps{
		   sh 'rm -rf assessmentdocker' 
	        sh 'git clone https://github.com/SumaVarshitha/assessmentdocker.git'
		    clonerepo()
		    }}
		 
        stage('build') {
            
		steps {
			

        docker.image("sumavarshitha/java-maven-node").inside(){
          sh "mvn clean package"
        }}
            
            
	    
        }
        stage('SonarQube Analysis'){
		  //agent { label 'master' }
		//tools
		//{ maven 'mvn'}
		 environment{
               sonarscanner = tool 'sonars'
                   }
            steps{
               withSonarQubeEnv('sonar'){
                   // sh '${sonarscanner}/bin/sonar-scanner -Dproject.settings=./sonar-project.properties'
		       //sh "${scannerHome}/bin/sonar-scanner"
              sh """ mvn -Dsonar.projectKeySumaVarshitha_assessmentdocker 
	    -Dsonar.organization=sumavarshitha
	    -Dsonar.projectName=assessmentdocker
     	     -Dsonar.projectVersion=1.0
	     -Dsonar.language=java
             -Dsonar.sources=src
             -Dsonar.java.binaries=.
             -Dsonar.host.url=https://sonarcloud.io/
             -Dsonar.login=23c3c4a2d8cdc3f94ecc357df8d681a601cb48f6
             -Dsonar.java.coveragePlugin=jacoco
	     -Dsonar.sourceEncoding=UTF-8
	     -Dsonar.coverage.jacoco.xmlReportPaths = target/site/jacoco/*.xml 
	     -Dsonar.exclusions = **/*.html,**/*.css,**/*.js,**/*.xml,assessmentdocker/src/main/java/com/puppet/sample/*.java=true	sonar:sonar"""
    
 
	       }
            }
        }

    }
        
      /*  stage("Quality Gate") {
            steps {
              timeout(time: 3, unit: 'MINUTES') {
                waitForQualityGate abortPipeline: true
              }
            }
        }*/
       
}

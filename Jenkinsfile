@Library(['shlib@master'])_
pipeline {  }
	
	 
    /*agent any
  
    stages {
	    stage('clonestage'){
		    steps{
		  // sh 'rm -rf assessmentdocker' 
	        //sh 'git clone https://github.com/SumaVarshitha/assessmentdocker.git'
		    clonerepo()
		    }}
		 
        stage('build') {
            steps {
			  
                 //docker.image("sumavarshitha/java-maven-node").inside(){
                     // sh "mvn clean package"
                  // }
		    dockerbuild()
                }
			
            
	    }
        
        stage('SonarQube Analysis'){
		
		 //environment{
               //scannerHome = tool 'sonars'
                   //}
          steps{
           //withSonarQubeEnv('sonar'){
                   // sh '${sonarscanner}/bin/sonar-scanner -Dproject.settings=./sonar-project.properties'
		     // sh "${scannerHome}/bin/sonar-scanner"
           // sh "$"
		    sonarqube()
	       //}
            }
       }

    
        
      stage("Quality Gate") {
            steps {
            // timeout(time: 3, unit: 'MINUTES') {
             //  waitForQualityGate abortPipeline: true
		    qualitygate()
             // }
           }
        }
    }
}*/

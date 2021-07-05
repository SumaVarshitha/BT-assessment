pipeline {
    agent any
  tools { 
        maven 'M3' 
        //jdk 'jdk8' 
    }
  
 
    stages {
		 
        stage('build') {
		steps {
		//	sh 'rm -rf BMIbeta' 
	    //    sh 'git clone https://github.com/SumaVarshitha/BMIbeta.git'
                sh "mvn clean package"
            
	    }
		

        }
    
    stage('sonar') {
	    
	    environment{
               scannerHome = tool 'sonars'
                   }
		steps {
			 withSonarQubeEnv('sonar'){
                    //sh '${sonarscanner}/bin/sonar-scanner -Dproject.settings=./sonar-project.properties'
		       sh "sonars/bin/sonar-scanner"
				 
			 }
    }
}
    }}

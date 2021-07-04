pipeline {
    agent any
  tools { 
        maven 'M3' 
        //jdk 'jdk8' 
    }
  
   
  /*  environment{
        sonarscanner = tool 'sonar'
    }*/
    stages {
	    //stage('remove'){
		 
        stage('build') {
		steps {
		//	sh 'rm -rf BMIbeta' 
	    //    sh 'git clone https://github.com/SumaVarshitha/BMIbeta.git'
                sh "mvn clean package"
            
	    }
        }
    }
}

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
    }
}

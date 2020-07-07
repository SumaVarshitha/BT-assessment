pipeline{
	
	/*libraries{
lib 'shlib'
}
    agent any 
    tools{
        maven "mvn"
    }
	stages{
            stage('build'){
                steps{
                    build 'build'
                }
                }
           stage('deploy'){
               steps{
               //	withCredentials([usernamePassword(credentialsId: 'tomcat', passwordVariable: 'password', usernameVariable: 'username'),string(credentialsId: 'TOMCAT_URL', variable: 'tomcat_url')]){
		//sh 'curl http://18.216.136.124:8080//manager/text/undeploy?path=/bunny -u admin:admin'
		//sh 'curl -v -u admin:admin -T target/java-webapp.war http://18.216.136.124:8080//manager/text/deploy?path=/bunny'
			dep() 
		}
		}
             }*/
	//agent none
	 agent {
			    docker { image 'sumavarshitha/java-maven-node' }
	
		//dockerfile true
	 }
    stages {
	    stage('clone'){
		  //  agent {
			 //   docker { image 'sumavarshitha/java-maven-node' }}
		    steps{
			    sh 'sudo rm -rf /var/lib/jenkins/workspace/mickey/BT-assessment'
			    sh 'git clone https://github.com/SumaVarshitha/BT-assessment.git'
		    }}}
        stage('build') {
            steps {
		   // agent {
	   //docker { image 'sumavarshitha/java-maven-node' }
                sh "mvn clean package"
            }
	    }}
	    
	    stage('sonar'){
		    steps{
			  //  agent 
			     withSonarQubeEnv('sonar') {
				     sh 'mvn  sonar:sonar'}}
              }
    
    }
}

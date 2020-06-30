pipeline{
    agent any 
    tools{
        maven "mvn"
    }
    stages{
      /*  stage('Git clone'){
            steps{
                sh ' rm -rf java-tomcat-maven-example'
            sh 'git clone --branch master http://SumaVarshitha:sumasuji268@github.com/SumaVarshitha/java-tomcat-maven-example.git'
            }
            
        }*/
            stage('build'){
                steps{
                    sh 'mvn clean install'
                }
                }
            stage('deploy to tomcat'){
                steps{
                  
                
      //	withCredentials([usernamePassword(credentialsId: 'tomcat', passwordVariable: 'password', usernameVariable: 'username'),string(credentialsId: 'TOMCAT_URL', variable: 'tomcat_url')]){
		
		
			 
			sh 'curl http://http://18.216.136.124/:8080//manager/text/undeploy?path=/bunny -u admin:admin'
		
		
			 
			sh 'curl -v -u admin:admin -T java-tomcat-maven-example/target/java-tomcat-maven-example.war http://http://18.216.136.124/:8080//manager/text/deploy?path=/bunny'
		
		
			 
			}
		
		
			 
	
            }
            
        
    }
}

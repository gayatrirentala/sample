pipeline {
   agent any
  environment{
     PATH = "/opt/maven/bin:$PATH"
  }
   stages {
     stage('SCM checkout'){
	   steps {
	     git branch: 'main', credentialsId: 'git', url: 'https://github.com/gayatrirentala/sample.git'
	   }
	 }
     
     stage('Maven Build'){
	   steps {
	     sh "mvn clean package"
	      sh "mv target/*.war target/pc.war" 	   
	   }
	 }
	   
	 stage('Deployment Dev'){
		 sshagent(['guidewire-pc]){
	            sh """
		    scp -o StrictHostkeyChecking=no target/pc.war devuser@pcmod.apr.mdi:/opt/tomcat8/wepapps/
		    ssh devuser@pcmod.apr.mdi /opt/tomcat8/bin/shutdown.sh
		    ssh devuser@pcmod.apr.mdi /opt/tomcat8/bin/startup.sh
		    """
			   
			   }
	       
	   }
	 }  
   }
}	  

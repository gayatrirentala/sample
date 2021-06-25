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
	   }
	 }
   }
}	  

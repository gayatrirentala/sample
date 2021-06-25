node{
stage('SCM checkout'){
  git branch: 'main', credentialsId: 'git', url: 'https://github.com/gayatrirentala/sample.git'
}

stage('packaging'){
 sh 'mvn clean package'
}
}

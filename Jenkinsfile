node{
stage('SCM checkout'){
  git 'https://github.com/gayatrirentala/sample.git'
}

stage('packaging'){
 sh 'mvn clean package'
}
}

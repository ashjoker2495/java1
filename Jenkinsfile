pipeline {
agent any 
stages{
stage('build') {
steps {
 sh 'ant -f build.xml'
}
}
stage('test'){
steps {
sh 'ant -f test.xml'
}
}
}
post {
always {
archive 'dist/*.jar'
}
}
}



pipeline {
agent any 
stages{
stage('build') {
steps {
 sh 'ant -f build.xml'
}
}
stage('unit test') {
steps { 
sh 'ant -f test.xml' 
junit 'reports/result.xml'
}
}
}}
post {
always {
archiveArtifacts artifacts: 'dist/*.jar', fingerprint: true
}
}




pipeline {
agent any 
options {
buildDiscards(logRotator(numTokeepstr: '2', artifactsnumTokeepstr: '1'))
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
}
post {
always {
archiveArtifacts artifacts: 'dist/*.jar', fingerprint: true
}
}
}



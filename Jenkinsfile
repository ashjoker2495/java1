pipeline {
agent any 
stages{

stage('unit test') {
steps {
   sh 'ant -f test.xml'
   junit 'reports/result.xml'
   }
 }
stage('build') {
 steps {
    sh 'ant -f build.xml'
   }
  }
 }

post {
always {
archiveArtifacts artifacts: 'dist/*.jar', fingerprint: true
}
}
}



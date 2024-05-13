pipeline {
agent any
stages {
stage('Build') {
steps {
bat 'mvn -B -DskipTests clean package'
}
}
stage('pmd') {
steps {
bat 'mvn pmd:pmd'
}
}
stage('test'){
  steps{
    bat 'mvn test'
  }
}
}
post {
always {
archiveArtifacts artifacts: '**/target/site/**', fingerprint: true
archiveArtifacts artifacts: '**/target/**/*.jar', fingerprint: true
archiveArtifacts artifacts: '**/target/**/*.war', fingerprint: true
}
}
}

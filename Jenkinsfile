pipeline {
  agent any
  tools {
    maven 'maven' 
       }
  stages {
    stage ('Build') {
      steps {
        sh 'mvn clean install -DskipTest'
      }
    }
    stage ('Deploy To Tomcat Server') {
      steps{
        script {
        deploy adapters: [tomcat9(credentialsId: 'Tomcat_deploymentI_D', path: '', url: 'http://35.180.34.193:8080/')], contextPath: 'live', onFailure: false, war: '**/*.war'
      }
     }
   }
 }
}


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
       deploy adapters: [tomcat9(credentialsId: 'TOMCAT', path: '', url: 'http://52.91.73.97:8080/')], contextPath: 'live', war: '**/*.war'
      }
     }
   }
 }
}


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
        deploy adapters: [tomcat9(credentialsId: 'b0b2d9a8-3fb5-4e83-9824-2712709ddaa3', path: '', url: 'http://13.39.18.6:8080/')], contextPath: 'live', war: '**/*.war'
      }
     }
   }
 }
}


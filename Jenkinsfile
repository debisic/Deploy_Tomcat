pipeline {
  agent any
  tools {
    maven 'Maven' 
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
        deploy adapters: [tomcat9(credentialsId: 'Deployer', path: '', url: 'http://18.209.228.246:8080')], contextPath: '/web', onFailure: false, war: '**/hello-world.war'
      }
     }
   }
 }
}


pipeline {
   agent any

   stages {
      stage('Get the code') {
         steps {
            git 'https://github.com/unixtrainingoct26/project20.git'
         }
      }
         stage('compile') {
         steps {
            sh '/var/lib/jenkins/tools/hudson.tasks.Maven_MavenInstallation/Maven363/bin/mvn compile'
         }
      }
         stage('Test') {
         steps {
            sh '/var/lib/jenkins/tools/hudson.tasks.Maven_MavenInstallation/Maven363/bin/mvn test'
         }
      }
        
         stage('Package') {
         steps {
            sh '/var/lib/jenkins/tools/hudson.tasks.Maven_MavenInstallation/Maven363/bin/mvn package'
         }
      } 
      
         stage('Deployment') {
         steps {
             echo 'Deployment'
            sh 'sudo cp /var/lib/jenkins/workspace/projet-pipelinejob/webapp/target/holy.war /usr/share/tomcat/webapps/'
            sh 'sudo systemctl restart tomcat'
         }
      }
   }
}

pipeline {

   agent any

   stages {
       stage('docker-compose') {
           steps {
              sh "docker-compose build"
              sh "docker-compose -f docker-compose.yml up -d"
              
           }
       }
   }
   post {
      always {
         sh "docker-compose down || true"
      }
   }   
}

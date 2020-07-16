pipeline {

   agent any

   stages {
       stage('docker-compose') {
           steps {
              sh "docker-compose build"
              sh 'docker-compose --tls'
              sh "docker-compose up -d"
              
           }
       }
   }
   post {
      always {
         sh "docker-compose down || true"
      }
   }   
}

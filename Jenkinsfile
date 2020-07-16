pipeline {

   agent any

   stages {
       stage('docker-compose') {
           steps {
              sh "docker-compose build"
       
              step([$class: 'DockerComposeBuilder', dockerComposeFile: 'docker-compose.yml', option: [$class: 'StartAllServices'], useCustomDockerComposeFile: true])
 
              
           }
       }
   }
   post {
      always {
         sh "docker-compose down || true"
      }
   }   
}

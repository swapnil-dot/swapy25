pipeline {

   agent any

   stages {
       stage('docker-compose file setup') {
           steps {
              sh 'echo "Running docker-compose build and deploy commands.........."'
              sh "docker-compose build"   
                    
           }
       }
      stage('Deploy'){
         steps{
            sh 'echo "deploying...."'
            step([$class: 'DockerComposeBuilder', dockerComposeFile: 'docker-compose.yml', option: [$class: 'StartAllServices'], useCustomDockerComposeFile: true])
              
         }
         
      }
   }
  
 post {
        always {
            echo 'One way or another, I have finished'
            cleanWs()
            /* clean up our workspace */
        }
        success {
            echo 'I succeeeded!'
        }
        unstable {
            echo 'I am unstable :/'
        }
        failure {
            echo 'I failed :('
        }
        changed {
            echo 'Things were different before...'
        }
    }
}


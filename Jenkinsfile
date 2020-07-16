pipeline{
    agent any
    stages{
        stage('Docker-compose'){
           steps{
             sh 'echo "Running docker-compose.yml......setting up containers!"'
             sh 'docker-compose build'
             
             step([$class: 'DockerComposeBuilder', dockerComposeFile: 'docker-compose.yml', option: [$class: 'StartService', scale: 1, service: 'java'], useCustomDockerComposeFile: false])
           
                }
           }
        
     }
     post{
       always{
           cleanWs()
             }
         }
}


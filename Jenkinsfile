pipeline{
    agent any
    stages{
        stage('Docker-compose'){
           steps{
             sh 'echo "Running docker-compose.yml......setting up containers!"'
             sh 'docker-compose up -d --force-recreate --tls'
                }
           }
        
     }
     post{
       always{
           cleanWs()
             }
         }
}


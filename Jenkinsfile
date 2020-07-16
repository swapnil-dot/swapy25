pipeline{
    agent any
    stages{
        stage('Docker-compose'){
           steps{
             sh 'echo "Running docker-compose.yml......setting up containers!"'
                }
           }
        
     }
     post{
       always{
           cleanWs()
             }
         }
}


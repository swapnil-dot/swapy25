pipeline{
    agent any
    stages{
        stage('Docker-compose'){
           steps{
             sh 'echo "Running docker-compose.yml......setting up containers!"'
             docker-compose up --tls -d
              
                }
           }
        
     }
     post{
       always{
           cleanWs()
             }
         }
}


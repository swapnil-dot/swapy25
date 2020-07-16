pipeline{
    agent any
    stages{
        stage('Docker-compose'){
           steps{
             sh 'echo "Running docker-compose.yml......setting up containers!"'
             sh 'docker-compose build'
             
             sh "docker-compose up -d"
                sh """
                    docker run --rm \                    
                        -v /var/run/docker.sock:/var/run/docker.sock:ro \                      
                        
                        swapy25/maven-is-up
                """
                 }
           }
        
     }
     post{
       always{
           cleanWs()
             }
         }
}


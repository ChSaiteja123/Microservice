pipeline {
    agent any

    stages {
        stage("Docker Build & Push"){
            steps{
                script{
                    withDockerRegistry(credentialsId: 'docker-cred'){   
                       sh "docker build -t checkoutservice ."
                       sh "docker tag checkoutservice saitejch/checkoutservice:latest "
                       sh "docker push saitejch/checkoutservice:latest "
                    }
                }
            }
        }
        
    }
}


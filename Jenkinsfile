pipeline {
    agent any

    stages {
        stage("Docker Build & Push"){
            steps{
                script{
                    withDockerRegistry(credentialsId: 'docker-cred'){   
                       sh "docker build -t shippingservice ."
                       sh "docker tag shippingservice saitejch/shippingservice:latest "
                       sh "docker push saitejch/shippingservice:latest "
                    }
                }
            }
        }
        
    }
}

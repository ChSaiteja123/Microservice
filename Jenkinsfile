pipeline {
    agent any

    stages {
        stage("Docker Build & Push"){
            steps{
                script{
                    withDockerRegistry(credentialsId: 'docker-cred'){   
                       sh "docker build -t productcatalogservice ."
                       sh "docker tag productcatalogservice saitejch/productcatalogservice:latest "
                       sh "docker push saitejch/productcatalogservice:latest "
                    }
                }
            }
        }
        
    }
}


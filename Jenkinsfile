pipeline {
    agent any

    stages {
        stage("Docker Build & Push"){
            steps{
                script{
                    withDockerRegistry(credentialsId: 'docker-cred'){   
                       sh "docker build -t frontend ."
                       sh "docker tag frontend saitejch/frontend:latest "
                       sh "docker push saitejch/frontend:latest "
                    }
                }
            }
        }
        
    }
}




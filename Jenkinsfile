pipeline {
    agent any

    stages {
        stage("Docker Build & Push"){
            steps{
                script{
                    withDockerRegistry(credentialsId: 'docker-cred'){   
                       sh "docker build -t loadgenerator ."
                       sh "docker tag loadgenerator saitejch/loadgenerator:latest "
                       sh "docker push saitejch/loadgenerator:latest "
                    }
                }
            }
        }
        
    }
}




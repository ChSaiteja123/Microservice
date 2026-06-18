pipeline {
    agent any

    stages {
        stage("Docker Build & Push"){
            steps{
                script{
                    withDockerRegistry(credentialsId: 'docker-cred'){   
                       sh "docker build -t emailservice ."
                       sh "docker tag emailservice saitejch/emailservice:latest "
                       sh "docker push saitejch/emailservice:latest "
                    }
                }
            }
        }
        
    }
}





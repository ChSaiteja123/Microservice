pipeline {
    agent any

    stages {
        stage("Docker Build & Push"){
            steps{
                script{
                    withDockerRegistry(credentialsId: 'docker-cred'){   
                       sh "docker build -t cartservice ."
                       sh "docker tag cartservice saitejch/cartservice:latest "
                       sh "docker push saitejch/cartservice:latest "
                    }
                }
            }
        }
        
    }
}

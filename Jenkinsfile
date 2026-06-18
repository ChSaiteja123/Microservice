pipeline {
    agent any

    stages {
        stage("Docker Build & Push"){
            steps{
                script{
                    withDockerRegistry(credentialsId: 'docker-cred'){   
                       sh "docker build -t currencyservice ."
                       sh "docker tag currencyservice saitejch/currencyservice:latest "
                       sh "docker push saitejch/currencyservice:latest "
                    }
                }
            }
        }
        
    }
}

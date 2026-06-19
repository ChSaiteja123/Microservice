pipeline {
    agent any

    stages {
        stage("Docker Build & Push"){
            steps{
                script{
                    withDockerRegistry(credentialsId: 'docker-cred'){   
                       sh "docker build -t recommendationservice ."
                       sh "docker tag recommendationservice saitejch/recommendationservice:latest "
                       sh "docker push saitejch/recommendationservice:latest "
                    }
                }
            }
        }
        
    }
}


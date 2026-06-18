pipeline {
    agent any

    stages {
        stage("Docker Build & Push"){
            steps{
                script{
                    withDockerRegistry(credentialsId: 'docker-cred'){   
                       sh "docker build -t paymentservice ."
                       sh "docker tag paymentservice saitejch/paymentservice:latest "
                       sh "docker push saitejch/paymentservice:latest "
                    }
                }
            }
        }
        
    }
}


}


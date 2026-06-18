pipeline {
    agent any

    stages {
        stage("Docker Build & Push"){
            steps{
                script{
                    withDockerRegistry(credentialsId: 'docker-cred'){   
                       sh "docker build -t adservice ."
                       sh "docker tag adservice saitejch/adservice:latest "
                       sh "docker push saitejch/adservice:latest "
                    }
                }
            }
        }
        
    }
}

}

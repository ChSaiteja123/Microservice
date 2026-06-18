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


}

pipeline {
    agent any

    stages {
        stage('Build & Tag Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'docker-cred', toolName: 'docker') {
                        sh "docker build -t saitejach/adservice:latest ."
                    }
                }
            }
        }
        
        stage('Push Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'docker-cred', toolName: 'docker') {
                        sh "docker push saitejach/adservice:latest "
                    }
                }
            }
        }
    }
}

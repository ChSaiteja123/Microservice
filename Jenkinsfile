pipeline {
    agent any

    stages {
        stage('deploy to k8s') {
            steps {
                withKubeCredentials(kubectlCredentials: [[caCertificate: '', clusterName: 'eks-web', contextName: '', credentialsId: 'k8s-token', namespace: 'webapps', serverUrl: 'https://077D05186241D36AC1C3404BAD2D0FC7.gr7.us-east-1.eks.amazonaws.com']]) {
                    sh "kubectl apply -f deployment-service.yml"
                    sleep 60
                }
            }
        }
    
   
        stage('verify deployment') {
            steps {
                withKubeCredentials(kubectlCredentials: [[caCertificate: '', clusterName: 'eks-web', contextName: '', credentialsId: 'k8s-token', namespace: 'webapps', serverUrl: 'https://077D05186241D36AC1C3404BAD2D0FC7.gr7.us-east-1.eks.amazonaws.com']]) {
                        sh "kubectl get all -n webapps"
                }
            }
        }
     }
}

pipeline { 
    agent any

    stages {
        stage('DeploytoEKS') {
            steps {
               withKubeCredentials(kubectlCredentials: [[caCertificate: '', clusterName: 'EKS-1', contextName: '', credentialsId: 'k8-token', namespace: 'webapps', serverUrl: 'https://E6F5B564B98D372EC59DE077638B3890.gr7.us-east-1.eks.amazonaws.com']]) {
                   sh "kubectl apply deployment-service.yml"
                   sleep 70
                }
            }
        }
    
        stage('verify deployment') {
            steps {
                withKubeCredentials(kubectlCredentials: [[caCertificate: '', clusterName: 'EKS-1', contextName: '', credentialsId: 'k8-token', namespace: 'webapps', serverUrl: 'https://E6F5B564B98D372EC59DE077638B3890.gr7.us-east-1.eks.amazonaws.com']]) {
                
                    sh "kubectl get aii -n webapps"
                }
            }
        }
    }
}

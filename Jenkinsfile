pipeline {
    agent any

    stages {
        stage('Deploy To Kubernetes') {
            steps {
                script {
                     withKubeCredentials(kubectlCredentials: [[caCertificate: '', clusterName: 'eks-26', contextName: '', credentialsId: 'k8s-cred', namespace: 'webapps', serverUrl: 'https://C1CBB027A5393E5CC02437DBF6DB4CB6.gr7.ap-south-1.eks.amazonaws.com']]) {
                         sh "kubectl apply -f deployment-service.yml"
                     }
                }
            }
        }
        
        stage('verify Deployment') {
            steps {
                script {
                     withKubeCredentials(kubectlCredentials: [[caCertificate: '', clusterName: 'eks-26', contextName: '', credentialsId: 'k8s-cred', namespace: 'webapps', serverUrl: 'https://C1CBB027A5393E5CC02437DBF6DB4CB6.gr7.ap-south-1.eks.amazonaws.com']]) {
                         sh "kubectl get svc -n webapps"
                     }
                }
            }
        }
    }
}

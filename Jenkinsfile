pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'docker build -t saailokesh/currencyservice:latest .'
            }
        }
        stage('Push') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'docker-cred') {
                        sh 'docker push saailokesh/currencyservice:latest'
                    }
                }
            }
        }
    }
}


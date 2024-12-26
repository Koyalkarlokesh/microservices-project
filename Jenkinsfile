pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'docker build -t saailokesh/recommendationservice:latest'
            }
        }
        stage('Push') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'docker-cred') {
                        sh 'docker push saailokesh/recommendationservice:latest'
                    }
                }
            }
        }
    }
}

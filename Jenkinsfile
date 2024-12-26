pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'docker build -t saailokesh/adservice:latest'
            }
        }
        stage('Push') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'docker-cred') {
                        sh 'docker push saailokesh/adservice:latest'
                    }
                }
            }
        }
    }
}


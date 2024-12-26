pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                dir('src') {
                    sh 'docker build -t saailokesh/cartservice:latest ./src/services'
                }
            }
        }
        stage('Push') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'docker-cred') {
                        sh 'docker push saailokesh/cartservice:latest'
                    }
                }
            }
        }
    }
}

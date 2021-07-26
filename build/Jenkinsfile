pipeline {
    environment {
        registry = "192.168.9.104:5000/test"
        registryUrl = "http://192.168.9.104:5000"
        registryCredential = 'nexus'
    }
    agent any
    stages {
        stage('Build docker image') {
            steps {
                sh 'docker build -t $registry:latest .'
            }
        }
        stage('Deploy docker image') {
            steps {
                withDockerRegistry([ credentialsId: registryCredential, url: registryUrl ]) {
                    sh 'docker push $registry:latest'
                }
            }
        }
     }
}

pipeline {
    agent any

    stages {
        stage('Build & Tag Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'sreeni-cred', toolName: 'docker') {
                        sh "docker build -t sreenivasuluramanaboina/checkoutservice:latest ."
                    }
                }
            }
        }
        
        stage('Push Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'sreeni-cred', toolName: 'docker') {
                        sh "docker push sreenivasuluramanaboina/checkoutservice:latest "
                    }
                }
            }
        }
    }
}

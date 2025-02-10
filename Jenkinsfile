pipeline { 
    agent any

    stages {
        stage('Build & Tag Docker Image') {
            steps {
                script {
                    dir('src') {

                    withDockerRegistry(credentialsId: 'sreeni-cred', toolName: 'docker') {
                        sh "docker build -t sreenivasuluramanaboina/cartservice:latest ."
                    }
                        }
                }
            }
        }
        
        stage('Push Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'sreeni-cred', toolName: 'docker') {
                        sh "docker push sreenivasuluramanaboina/cartservice:latest "
                    }
                }
            }
        }
    }
}

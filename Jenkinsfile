pipeline {
    agent any

    stages {
        stage('clone') {
            steps {
                checkout scmGit(branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/Ramya249/CandyStore.git']]) 
            }
        }
        stage('docker') {
            steps {
                script {
                withDockerRegistry(url: 'https://app.docker.com/') {
                         sh 'docker build -t Ramya249/CandyStore .'
                         sh 'docker push Ramya249/CandyStore:latest'
                   }
               }
            }
        }
    }
}

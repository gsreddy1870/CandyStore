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
                withDockerRegistry(credentialsId: 'doc') {
                         sh 'docker build -t ramya249/CandyStore .'
                         sh 'docker push ramya249/CandyStore:latest'
                   }
               }
            }
        }
    }
}

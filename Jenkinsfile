pipeline {
    agent any

    stages {
        stage('clone') {
            steps {
                checkout scmGit(branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/gsreddy1870/CandyStore.git']]) 
            }
        }
        stage('docker') {
            steps {
                script {
                withDockerRegistry(credentialsId: 'dock', toolName: 'docker') {
                         sh 'docker build -t gsreddy1870/candystore .'
                         sh 'docker push gsreddy1870/candystore:latest'
                   }
               }
            }
        }
    }
}

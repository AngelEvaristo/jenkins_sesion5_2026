pipeline {
    agent any

    stages {
        stage('Clone from github'){
            steps {
                checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'AngelEvaristo', url: 'https://github.com/AngelEvaristo/jenkins_sesion5_2026.git']])                
            }            
        }
        stage ('Restore'){
            steps {
                bat 'dotnet restore'
            }
        }
        stage ('Build'){
            steps {
                bat 'dotnet build'
            }
        }
    }
}
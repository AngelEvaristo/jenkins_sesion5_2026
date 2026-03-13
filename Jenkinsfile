pipeline {
    agent any

    stages {
        stage('Clone from github'){
            steps {
                checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'AngelEvaristo', url: 'https://github.com/AngelEvaristo/jenkins_sesion5_2026.git']])                
            }            
        }
        stage ('Validacion de make'){
            steps {
                bat 'make --version'
            }
        }

        stage ('Restore con make'){
            bat 'make restore'
        }

        stage ('Build con make'){
            bat 'make build'
        }

        stage ('test con make'){
            bat 'make test'
        }

    }
}
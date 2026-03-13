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
                powershell 'scripts/restore.ps1'
            }
        }
        stage ('Build'){
            steps {
                powershell 'scripts/build.ps1'
            }
        }
        stage ('Test'){
            steps {
                powershell 'scripts/test.ps1'
            }
        }        
    }
}
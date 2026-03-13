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
            steps {
                bat 'make restore'
            }
            
        }

        stage ('Build con make'){
            steps {
                bat 'make build'
            }
            
        }

        stage ('test con make'){
            steps {
                bat 'make test'
            }            
        }

        stage ('Publish'){
            steps {
                bat 'make publish'
                archiveArtifacts artifacts: 'published/**'
            }
        }

    }

    post {
        always {
            cleanWs()
        }
        success {
            echo "Compilacion completada con exito."
        }
        failure {
            echo "Error en compilacion"
        }
    }
}
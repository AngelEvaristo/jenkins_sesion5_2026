pipeline {
    agent any

    stages {
        stage('load template'){
            steps {
                script {
                    dir('pipeline-remote'){
                        checkout([
                            $class: 'GitSCM',
                            branches: [[name: '*/main']],
                            userRemoteConfigs: [[
                                url: 'https://github.com/AngelEvaristo/librerias_jenkins_2026',
                                credentialsId: 'AngelEvaristo'
                            ]]
                        ])                        
                    }

                    def remote = load 'pipeline-remote/pipelines/buildytest.groovy'
                    remote.call('Proyecto dotnet',false)
                }                
            }            
        }

    }
}
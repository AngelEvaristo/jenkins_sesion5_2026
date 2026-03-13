@Library('shared-lib@main') _

import org.example.stringtools

pipeline {
    agent any
    stages {
        stage('prueba'){
            steps{
                script {
                    hello('dotnet')

                    def tag = stringtools.tag(env.BRANCH_NAME,env.BUILD_NUMBER)
                    echo "Tag del build es ${tag}"
                }
            }
        }
    }
}
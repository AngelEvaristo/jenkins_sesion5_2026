@Library('shared-lib-2026@main') _

pipeline {
    agent any

    stages {
        stage('Restore') {
            steps {
                dotnetRestore(solution: 'MyMinimapApi.sln')
            }
        }

        stage('Build') {
            steps {
                dotnetBuild(solution: 'MyMinimapApi.sln')
            }
        }

        stage('Test') {
            steps {
                dotnetTest(project: 'MyMinimapApi.Tests/MyMinimapApi.Tests.csproj')
            }
        }

        stage('Publish') {
            steps {
                dotnetPublish(
                    project: 'MyMinimapApi.Api/MyMinimapApi.Api.csproj',
                    output: 'publish'
                )

                archiveArtifacts artifacts: 'publish/**', fingerprint: true
            }
        }
    }
}

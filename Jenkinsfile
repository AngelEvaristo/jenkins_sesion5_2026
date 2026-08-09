@Library('shared-lib-2026@main') _

pipeline {
    agent any

    stages {
        stage('Restore') {
            steps {
                dotnetRestore(solution: 'MyMinimalApi.sln')
            }
        }

        stage('Build') {
            steps {
                dotnetBuild(solution: 'MyMinimalApi.sln')
            }
        }

        stage('Test') {
            steps {
                dotnetTest(project: 'MyMinimalApi.Tests/MyMinimalApi.Tests.csproj')
            }
        }

        stage('Publish') {
            steps {
                dotnetPublish(
                    project: 'MyMinimalApi.Api/MyMinimalApi.Api.csproj',
                    output: 'publish'
                )

                archiveArtifacts artifacts: 'publish/**', fingerprint: true
            }
        }
    }
}

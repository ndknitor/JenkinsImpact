pipeline {
    agent any
    stages {
        stage('Clone repository') {
            steps {
                    git branch: 'main', credentialsId: 'Ndkn', url: 'https://github.com/ndknitor/JenkinsImpact'
            }
        }
        stage('Build') {
            steps {
                sh 'dotnet restore'
                sh 'dotnet build --no-restore'
            }
        }
        stage('Test') {
            steps {
                sh 'dotnet test'
            }
        }
        stage('Run') {
            steps {
                sh 'dotnet run --project JenkinsImpact'
            }
        }
    }
}
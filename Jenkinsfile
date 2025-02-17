pipeline {
    agent any
    environment {
        DOTNET_ROOT = "/usr/local/share/dotnet"
        PATH = "$DOTNET_ROOT:$PATH"
    }
    stages {
        stage('Restore Dependencies') {
            steps {
                sh 'dotnet restore'
            }
        }
        stage('Build Project') {
            steps {
                sh 'echo $PATH' 
                sh 'dotnet build --configuration Release'
            }
        }
        stage('Run dotnet tests') {
            steps {
                sh 'dotnet test'
            }
        }
    }
}
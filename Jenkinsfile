pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Restore dependencies') {
            steps {
                bat 'dotnet restore'
            }
        }

        stage('Build the Project') {
            steps {
                bat 'dotnet build --no-restore'
            }
        }

        stage('Run Test') {
            steps {
                bat 'dotnet test --no-build --verbosity normal'
            }
        }
    }
}

pipeline {
    agent any

    stages {

        stage('Restore dependencies') {
            when {
                branch 'main'
            }
            steps {
                bat 'dotnet restore Homies.sln'
            }
        }

        stage('Build the project') {
            when {
                branch 'main'
            }
            steps {
                bat 'dotnet build Homies.sln --no-restore -c Release'
            }
        }

        stage('Run the tests') {
            when {
                branch 'main'
            }
            steps {
                bat 'dotnet test Homies.sln --no-build -c Release --verbosity normal'
            }
        }
    }
}
pipeline {
    agent any

    triggers {
        pollSCM('H/1 * * * *')
    }

    stages {
        stage('run Checkout step') {
            steps {
                checkout scm
            }
        }

        stage('run Restore Dependencies step') {
            steps {
                sh 'dotnet restore'
            }
        }

        stage('run Build step') {
            steps {
                sh 'dotnet build --no-restore'
            }
        }

        stage('run Test step') {
            steps {
                sh 'dotnet test --no-build --verbosity normal'
            }
        }
    }
}
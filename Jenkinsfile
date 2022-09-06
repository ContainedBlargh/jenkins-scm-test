pipeline {
    agent any
    
    stages {
        stage('Pull repositoy') {
            steps {
                pwsh('git pull origin master')
            }
        }
        stage('Setup containers') {
            steps {
                pwsh('docker container list -a')
                pwsh('docker compose up -d')
            }
        }
        stage('Stop containers') {
            steps {
                pwsh('docker compose down')
            }
        }
    }
}
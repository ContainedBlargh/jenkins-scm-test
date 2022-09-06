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
                pwsh('docker compose up -d')
            }
        }
        stage('Test containers') {
            script {
                output = pwsh('docker container list -a')
            }
            echo "$output"
        }
        stage('Stop containers') {
            steps {
                pwsh('docker compose down')
            }
        }
    }
}
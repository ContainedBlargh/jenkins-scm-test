pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                echo "$GIT_BRANCH"
            }
        }
        stage('Build containers') {
            steps {
                pwsh('docker container list -a')
                pwsh('docker compose up -d')
            }
        }
    }
}
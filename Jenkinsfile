pipeline {
    agent { 
        docker { 
            image 'mcr.microsoft.com/playwright:v1.51.0-noble'
            args '-e NPM_CONFIG_CACHE=/tmp/.npm' 
        } 
    }
    stages {
        stage('install playwright') {
            steps {
                sh 'sudo chown -R 501:20 "/.npm"'
                sh 'npm i -D @playwright/test'
                sh 'npx playwright install'
            }
        }
        stage('test') {
            steps {
            sh 'npx playwright test --list'
            sh 'npx playwright test'
            }
        }
    }
}
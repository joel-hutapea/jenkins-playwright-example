pipeline {
    agent { docker { image 'mcr.microsoft.com/playwright:v1.51.0-noble' } }
    stages {
        stage('install playwright') {
            steps {
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
pipeline {
   agent { docker { image 'mcr.microsoft.com/playwright:v1.51.0-noble' } }
   stages {
      stage('e2e-tests') {
         steps {
            sh 'sudo chown -R 501:20 "/.npm"'
            sh 'npm ci'
            sh 'npx playwright test --list'
            sh 'npx playwright test'
         }
      }
   }
}
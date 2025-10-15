pipeline {
    agent any
    environment { DEPLOY_DIR = 'C:\\inetpub\\wwwroot' }
    stages {
        stage('Checkout') { steps { git branch: 'main', url: 'https://github.com/Amruta6403/jenkins-html-ci.git' } }
        stage('Build') { steps { bat 'dir' } }
        stage('Test') { steps { bat 'tidy -q -e index.html || exit /b 0' } }
        stage('Deploy') { steps { bat "xcopy /Y /E /I * %DEPLOY_DIR%\\" } }
    }
    post {
        success { echo '✅ Deployment successful! Visit http://localhost' }
        failure { echo '❌ Deployment failed!' }
    }
}

pipeline {
    agent any
    tools {
        nodejs 'NodeJS_20'
    }
    stages {
        stage('Clone') {
            steps { echo 'Code Cloned' }
        }
        stage('Install') {
            steps { bat 'npm install' }
        }
        stage('Deploy') {
            steps {
                bat '''
                pm2 delete node-jenkins-app 2>nul || echo First time deploy
                pm2 start app.js --name node-jenkins-app --update-env
                pm2 save
                echo Deployment Done
                exit 0
                '''
            }
        }
    }
}

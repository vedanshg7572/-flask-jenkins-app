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
                nodejs('NodeJS_20') {
                    bat '''
                    echo "Stopping old app..."
                    taskkill /F /IM node.exe /T 2>nul || echo "No old process"
                    timeout /t 3
                    echo "Starting new app..."
                    start /B node app.js
                    timeout /t 5
                    echo "App deployed on port 3000"
                    '''
                }
            }
        }
    }
}

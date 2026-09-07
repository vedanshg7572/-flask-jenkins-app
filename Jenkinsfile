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
                    bat 'taskkill /F /IM node.exe /T 2>nul || echo No old process'
                    bat 'start /B node app.js'
                    echo 'App deployed successfully on port 3000'
                }
            }
        }
    }
}

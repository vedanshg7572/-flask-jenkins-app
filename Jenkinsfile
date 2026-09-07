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
        stage('Run') {
            steps {
                nodejs('NodeJS_20') {
                    bat 'node --check app.js'
                    echo 'App verified successfully'
                }
            }
        }
    }
}

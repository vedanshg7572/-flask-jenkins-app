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
            steps { bat 'node app.js' }
        }
    }
}

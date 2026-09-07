pipeline {
    agent any
    stages {
        stage('Install') {
            steps {
                bat 'pip install -r requirements.txt'
            }
        }
        stage('Test Flask') {
            steps {
                bat 'python -c "import flask; print(flask.__version__)"'
            }
        }
        stage('Run App') {
            steps {
                bat 'python app.py'
            }
        }
    }
}

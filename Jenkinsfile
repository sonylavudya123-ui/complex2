pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Build and Test') {
            steps {
                bat 'python -m py_compile app.py'
                bat 'python -m unittest'
            }
        }
        stage('Package') {
            steps {
                bat 'powershell -Command "Compress-Archive -Path app.py -DestinationPath app.zip -Force"'
            }
        }
    }
}
pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t ci-python-app .'
            }
        }

        stage('Run Tests') {
            steps {
                sh 'docker run --rm ci-python-app pytest'
            }
        }
    }
}

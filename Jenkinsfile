
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
                bat 'mvn clean verify'
            }
        }

        stage('Build Docker Image') {
            steps {
                bat 'docker build -t smart-study-planner .'
            }
        }
    }
}

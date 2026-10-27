
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
                bat '"C:\\Users\\Kavya\\AppData\\Local\\Programs\\DockerDesktop\\resources\\bin\\docker.exe" build -t smart-study-planner .'
            }
        }
    }
}

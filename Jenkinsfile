
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

        stage('Deploy Application') {
            steps {
                bat '''
                "C:\\Users\\Kavya\\AppData\\Local\\Programs\\DockerDesktop\\resources\\bin\\docker.exe" stop smart-study-planner || exit /b 0
                "C:\\Users\\Kavya\\AppData\\Local\\Programs\\DockerDesktop\\resources\\bin\\docker.exe" rm smart-study-planner || exit /b 0
                "C:\\Users\\Kavya\\AppData\\Local\\Programs\\DockerDesktop\\resources\\bin\\docker.exe" run -d --name smart-study-planner -p 8080:8080 smart-study-planner
                '''
            }
        }
    }
}

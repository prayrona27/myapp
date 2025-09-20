pipeline {
    agent any   // Run on any available Jenkins node

    stages {
        stage('Checkout') {
            steps {
                // Checkout code from the repository automatically
                checkout scm
            }
        }

        stage('Build') {
            steps {
                // Build Maven project on Windows
                bat 'mvn clean install'
            }
        }

        stage('Test') {
            steps {
                // Run tests
                bat 'mvn test'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying the application...' 
                // Add your deploy commands here
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed. Check logs!'
        }
    }
}

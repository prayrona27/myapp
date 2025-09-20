pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/prayrona27/myapp.git'
            }
        }
        stage('Build') {
            steps {
                bat 'mvn clean install'
            }
        }
        stage('Test') {
            steps {
                bat 'mvn test'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying...'
            }
        }
    }
}

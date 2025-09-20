pipeline {
  agent {
    docker {
      image 'maven:3.8.7-openjdk-11'
      args '-v $HOME/.m2:/root/.m2'
    }
  }
  stages {
    stage('Checkout') {
      steps {
        // If Jenkins Pipeline is configured to repo+Jenkinsfile via SCM this git step isn't required.
        git branch: 'main', url: 'https://github.com/youruser/yourrepo.git'
      }
    }
    stage('Build & Test') {
      steps {
        sh 'mvn -B clean test'
      }
    }
  }
  post {
    always {
      junit 'target/surefire-reports/*.xml'
      archiveArtifacts artifacts: 'target/*.jar', allowEmptyArchive: true
    }
  }
}

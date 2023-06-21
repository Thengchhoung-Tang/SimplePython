pipeline {
  agent any

  stages {
    // stage('Checkout') {
    //   steps {
    //     // Checkout code from Git repository
    //     git 'https://github.com/Thengchhoung-Tang/SimplePython.git'
    //   }
    // }

    stage('Build Docker Image') {
      steps {
        // Build Docker image
        sh 'docker build -t simplepython .'
      }
    }

    stage('Run Docker Container') {
      steps {
        // Run Docker container
        sh 'docker run -d simplepython'
      }
    }
  }
}

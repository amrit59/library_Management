pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {
                echo 'Cloning repository...'
                // Clone the repository using the scm (source code management)
                checkout scm
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    // Build Docker image
                    bat 'docker build -t library:latest .'
                }
            }
        }

        stage('Run Container') {
            steps {
                script {
                    // Run Docker container
                    bat 'docker run -d -p 3000:80 library:latest'
                }
            }
        }

        stage('Done') {
            steps {
                echo 'Build and Run complete!'
            }
        }
    }
}
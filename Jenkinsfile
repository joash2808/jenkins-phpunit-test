pipeline {
    agent {
        docker {
            image 'composer:latest'
            // You can optionally specify other Docker-related settings here.
            // For example, 'args' or 'registryCredentials' if needed.
        }
    }
    stages {
        stage('Build') {
            steps {
                // Use 'sh' to execute shell commands
                script {
                    sh 'composer install' // Use 'script' block for multiple commands
                    git '/home'           // The correct syntax is 'git url: "/home"'
                }
            }
        }
        stage('Test') {
            steps {
                sh './vendor/bin/phpunit tests'
            }
        }
    }
}
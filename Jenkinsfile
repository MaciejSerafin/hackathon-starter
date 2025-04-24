pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Krok do klonowania repozytorium
                git 'https://github.com/MaciejSerafin/hackathon-starter.git'
            }
        }

        stage('Build') {
            steps {
                script {
                    // Komenda do kompilacji aplikacji
                    echo 'Building the application...'
                    // Wstaw odpowiednią komendę budowania np. `npm install` dla Node.js
                    sh 'npm install' 
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    // Komenda do uruchamiania testów aplikacji
                    echo 'Running tests...'
                    // Wstaw odpowiednią komendę testowania, np. `npm test`
                    sh 'npm test'
                }
            }
        }
    }

    post {
        success {
            echo 'Pipeline executed successfully!'
        }
        failure {
            echo 'Pipeline failed. Check logs for details.'
        }
    }
}

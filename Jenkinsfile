pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/MaciejSerafin/hackathon-starter.git'
            }
        }

        stage('Install Node.js') {
            steps {
                script {
                    // Instalacja Node.js 20.x (najbardziej aktualna LTS)
                    echo 'Installing Node.js and npm...'
                    sh 'curl -sL https://deb.nodesource.com/setup_20.x | bash -'
                    sh 'apt-get install -y nodejs'  // Nie używaj `sudo`, bo to może być problematyczne w Jenkinsie
                }
            }
        }

        stage('Build') {
            steps {
                script {
                    echo 'Building the application...'
                    sh 'npm install'
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    echo 'Running tests...'
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

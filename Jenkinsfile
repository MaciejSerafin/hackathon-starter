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
                    // Instalacja Node.js i npm na maszynie roboczej
                    echo 'Installing Node.js and npm...'
                    sh 'curl -sL https://deb.nodesource.com/setup_16.x | bash -'
                    sh 'sudo apt-get install -y nodejs'
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

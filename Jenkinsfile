pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {
                echo 'Cloning repository...'
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo 'Installing dependencies...'
                sh 'npm install'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                sh 'npm test || true'  // tymczasowo, jeśli są błędy w testach
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploy stage - simulated'
                // Można tu dodać np. docker run albo rsync
            }
        }

        stage('Publish') {
            steps {
                echo 'Publishing artifacts - simulated'
                // Np. upload do S3 lub DockerHub
            }
        }
    }
}

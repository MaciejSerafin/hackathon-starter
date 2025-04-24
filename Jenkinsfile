pipeline {
    agent {
        docker {
            image 'node:18'
            args '-v $HOME/.npm:/root/.npm' // opcjonalnie: cache dla npm
        }
    }

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
                sh 'npm test || true'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploy stage - simulated'
            }
        }

        stage('Publish') {
            steps {
                echo 'Publishing artifacts - simulated'
            }
        }
    }
}

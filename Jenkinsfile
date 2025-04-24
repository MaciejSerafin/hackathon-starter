pipeline {
    agent any

    environment {
        // Określ zmienne środowiskowe, jeśli są potrzebne
    }

    stages {
        stage('Commit') {
            steps {
                script {
                    // Przykład: Komitowanie zmian w repozytorium, jeśli to wymagane
                    // Skrypt do wykonania commit, np.:
                    // sh 'git commit -m "Automatyczny commit"'
                }
            }
        }

        stage('Clone') {
            steps {
                script {
                    // Klonowanie repozytorium, jeśli nie jest dostępne lokalnie
                    git 'https://github.com/MaciejSerafin/hackathon-starter.git'
                }
            }
        }

        stage('Build') {
            steps {
                script {
                    // Budowanie projektu (np. instalacja zależności w Node.js)
                    sh 'npm install'  // Możesz dostosować to do swojego projektu
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    // Uruchamianie testów jednostkowych (np. dla aplikacji Node.js)
                    sh 'npm test'  // Przykład testów w Node.js
                }
            }
        }
    }
}

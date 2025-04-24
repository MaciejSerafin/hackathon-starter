pipeline {
    agent any
    
    triggers {
        // Możesz ustawić ręczne uruchomienie pipeline'a, np. przez "Build Now" w Jenkinsie
        // Można także dodać trigger na commit do repozytorium
        // np. trigger co 5 minut: cron('H/5 * * * *')
        // lub na podstawie push do gałęzi:
        // pollSCM('* * * * *')  // Aktywacja na każde zmiany w repozytorium
    }

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
        
        // Możesz dodać inne etapy jak Deploy, jeśli chcesz, np. deploy do środowiska produkcyjnego
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

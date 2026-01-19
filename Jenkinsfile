pipeline {
    agent any

    stages {

        stage('Clone Repository') {
            steps {
                git branch: 'master',
                    url: 'https://github.com/HamzaAITMOUHAOUALLA/react-express-mysql.git'
            }
        }

        stage('Build Docker Images') {
            steps {
                bat 'docker compose build'
            }
        }

        stage('Run Containers') {
            steps {
                bat 'docker compose up -d'
            }
        }
    }

    post {
        success {
            echo '✅ Pipeline exécuté avec succès'
        }
        failure {
            echo '❌ Erreur dans le pipeline'
        }
    }
}

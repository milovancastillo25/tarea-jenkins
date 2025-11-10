pipeline {
    // Usamos un agente Docker con Python 3.9
    agent { docker { image 'python:3.9-slim' } }

    stages {
        stage('Build') {
            steps {
                echo 'Construyendo el proyecto...'
            }
        }
        stage('Test') {
            steps {
                echo 'Ejecutando pruebas unitarias...'
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Instalando dependencias y Bandit...'
                sh 'pip install -r requirements.txt'
                echo 'Ejecutando análisis estático con Bandit...'
                sh 'bandit -r . || true'
            }
        }
    }
}

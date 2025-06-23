pipeline {
    agent any
    tools {
        maven 'maven'
        jdk 'JDK11'
    }
    stages {
        stage('Clonar') {
            steps {
                git url: 'https://github.com/cgarrido-a/saludoapp.git', branch: 'main'
            }
        }
        stage('Compilar') {
            steps {
                sh 'mvn clean compile'
            }
        }
        stage('Probar') {
            steps {
                sh 'mvn test'
            }
        }
        stage('Empaquetar') {
            steps {
                sh 'mvn package'
            }
        }
    }
    post {
        success {
            echo "🎉 El build fue exitoso"
        }
        failure {
            echo "💥 El build falló"
        }
    }
}
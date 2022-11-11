pipeline{
    agent any

    stages {
        
        stage('Clean') {
            steps {
                cleanWs()
            }
        }

        stage('Compile Code') {
            steps {
                sh "./mvnw clean compile -e"
            }
        }

        stage('Test Code') {
            steps {
                sh "./mvnw clean test -e"
            }
        }

        stage('Jar Code') {
            steps {
                sh "./mvnw clean package -e"
            }
        }

        stage('Run Code') {
            steps {
                sh "./mvnw spring-boot:run"
            }
        }
    }
}
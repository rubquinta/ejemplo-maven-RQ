pipeline {
    agent any
    stages {  
        stage('Compile Code')
        {
            steps {
                sh "./mvnw clean compile -e"
            }
        }
        stage('Test Code') {
            steps 
            {
                sh "./mvnw clean test -e"
            }
        }
        stage('Jar Code') {
            steps 
            {
                sh "/mvnw clean package -e"
            }
        }
        stage('Run Code') {
            steps {
                sh "nohup bash mvnw spring-boot:run &"
			  sleep 25
            }
        }
    }
}
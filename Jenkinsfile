pipeline {
    agent any
    stages {    
        stage('Compile Code') 
        {
            steps {
                echo 'TODO: Compile'
                sh "./mvnw clean compile -e"
            }
        }
        stage('Test Code') 
        {
            steps {
                echo 'TODO: Test'
                sh "./mvnw clean test -e"
            }
        }
        stage('Build') 
        {
            steps {
                echo 'TODO: Package'
                sh "./mvnw clean package -e"
            }
        } 
        stage('SonarQube analysis') 
        {
            steps {
                withSonarQubeEnv(credentialsId: 'SoniToken', installationName: 'Sonita') { // You can override the credential to be used
            sh './mvnw org.sonarsource.scanner.maven:sonar-maven-plugin:3.7.0.1746:sonar'
            }
            }
        }   
        stage('Run Code') 
        {
            steps {
                echo 'TODO: running'
                sh "nohup bash mvnw spring-boot:run &"
                sleep 25
            }
        }
    }
}

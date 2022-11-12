pipeline {
    agent any
    stages {
        stage('SonarQube analysis') 
        {
            withSonarQubeEnv(credentialsId: 'squ_1320c719e926aba9e8599b1e751d717e1acdafee', 
            installationName: 'My SonarQube Server') 
            { // You can override the credential to be used
            sh 'mvn org.sonarsource.scanner.maven:sonar-maven-plugin:3.7.0.1746:sonar'
            }
        }
        stage('Compile Code') 
        {
            steps {
                echo 'TODO: build'
                sh "./mvnw clean compile -e"
            }
        }
        stage('Test Code') 
        {
            steps {
                echo 'TODO: test'
                sh "./mvnw clean test -e"
            }
        }
        stage('Jar Code') 
        {
            steps {
                echo 'TODO: package'
                sh "./mvnw clean package -e"
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
        stage('Testing')
        {
             steps { 
                 echo 'TODO: Testing 1 llamada simple'
                 sh "curl -X GET 'http://localhost:8081/rest/mscovid/test?msg=TestingSimple1'"
            }
        }
    }
}

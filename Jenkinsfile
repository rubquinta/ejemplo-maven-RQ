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
                sh "docker run -it --rm -v $(pwd):/code --workdir /code maven mvn clean compile -e"
            }
        }

        stage('Test Code') {
            steps {
                sh "docker run -it --rm -v $(pwd):/code --workdir /code maven mvn clean test -e"
            }
        }

        stage('Jar Code') {
            steps {
                sh "docker run -it --rm -v $(pwd):/code --workdir /code maven mvn clean package -e"
            }
        }

        stage('Run Code') {
            steps {
                sh "docker run -it --rm -p 8081:8081  -v $(pwd):/code --workdir /code maven mvn spring-boot:run"
            }
        }
    }
}
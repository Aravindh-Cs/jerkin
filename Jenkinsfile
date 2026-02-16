pipeline {
    agent any

    tools {
        jdk 'C:\Program Files\Java\jdk-11.0.17'
        maven 'Maven39'
    }

    stages {
        stage('Build') {
            steps {
                bat 'mvn clean package'
            }
        }

        stage('Deploy to Tomcat') {
            steps {
                deploy adapters: [tomcat9(
                    credentialsId: 'tomcat-creds',
                    url: 'http://localhost:8080'
                )],
                contextPath: 'myapp',
                war: 'target\\myapp.war'
            }
        }
    }
}

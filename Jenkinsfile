pipeline {
    agent any

    tools {
        jdk 'JDK11'
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

pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo "Code pulled from GitHub successfully"
                bat 'git --version'
                bat 'dir'
            }
        }
    }
}

pipeline {
    agent any
    stages {
        stage('Compile') {
            steps {
                sh 'echo Compile > /tmp/test'
            }
        }
        stage('Unit Tests') {
            steps {
                sh 'cat /tmp/test'
            }
        }
    }
}

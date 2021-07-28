pipeline {
    agent any
    stages {
        stage('Compile') {
            node("mypod") {
                steps {
                    sh 'mvn clean package -DskipTests=true'
                }
            }
        }
        stage('Unit Tests') {
            node("mypod") {
                steps {
                    sh 'mvn surefire:test'
                }
            }
        }
         stage('Integration Tests') {
            node("mypod") {
                steps {
                    sh 'mvn failsafe:integration-test'
                }
            }
        }
    }
    post {
        always {
            junit 'target/surefire-reports/TEST-*.xml'
        }
    }
}

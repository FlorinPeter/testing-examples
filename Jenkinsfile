node("maven") { 
    stage('Compile') {
        sh 'pwd'
        sh 'ls -la'
        sh 'mvn clean package -DskipTests=true'
    }
    stage('Unit Tests') {
        sh 'mvn surefire:test'
    }
     stage('Integration Tests') {
        sh 'mvn failsafe:integration-test'
    }
    
    post {
        always {
            junit 'target/surefire-reports/TEST-*.xml'
        }
    }
}

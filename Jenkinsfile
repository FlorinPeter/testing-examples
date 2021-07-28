node("maven") { 
    stage('Compile') {
        sh 'git clone https://github.com/FlorinPeter/testing-examples.git'
        sh 'cd testing-examples'
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
            junit 'testing-examples/target/surefire-reports/TEST-*.xml'
        }
    }
}

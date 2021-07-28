node("maven") { 
    stage('Compile') {
        sh 'git clone https://github.com/FlorinPeter/testing-examples.git'
        sh 'cd testing-examples;pwd;ls -la'
        sh 'cd testing-examples;mvn clean package -DskipTests=true'
    }
    stage('Unit Tests') {
        sh 'cd testing-examples;mvn surefire:test'
    }
     stage('Integration Tests') {
        sh 'cd testing-examples;mvn failsafe:integration-test'
        junit 'testing-examples/target/surefire-reports/TEST-*.xml' 
    }
}

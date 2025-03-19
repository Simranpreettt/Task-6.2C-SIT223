pipeline {
    agent any
    environment {
        EMAIL = 'simranpreetkaur23105@gmail.com'
    }
    stages {
        stage('Test Email') {
            steps {
                echo 'Testing email sending...'
            }
        }
    }
    post {
        always {
            emailext subject: "Email Test Result: ${currentBuild.currentResult}",
                     to: "${env.EMAIL}",
                     attachLog: true,
                     body: "Test email from Jenkinsfile."
        }
    }
}

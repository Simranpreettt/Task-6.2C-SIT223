pipeline {
    agent any
    environment {
        EMAIL = 'xr045jss@gmail.com'
    }
    stages {
        stage('Build') {
            steps {
                echo 'Build stage is running...'
            }
        }
        stage('Notify') {
            steps {
                emailext subject: "Build ${env.JOB_NAME} #${env.BUILD_NUMBER} - ${currentBuild.currentResult}",
                         to: "${env.EMAIL}",
                         body: "Job result: ${currentBuild.currentResult}\nSee details at ${env.BUILD_URL}",
                         attachLog: true
            }
        }
    }
}

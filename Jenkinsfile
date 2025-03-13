pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Checking out code...'
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo 'Building HTML project...'
            }
        }

        stage('Test') {
            steps {
                echo 'Running basic tests...'
            }
        }

        stage('Notify') {
            steps {
                echo 'Notification stage placeholder.'
            }
        }
    }

    post {
        success {
            mail to: 'jd.saravanan93@gmail.com',
                 subject: "✅ Jenkins Build Success: ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                 body: "Good news! Your Jenkins build succeeded.\nCheck it here: ${env.BUILD_URL}"
        }
        failure {
            mail to: 'jd.saravanan93@gmail.com',
                 subject: "❌ Jenkins Build Failed: ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                 body: "Oops! Your Jenkins build failed.\nCheck it here: ${env.BUILD_URL}"
        }
    }
}

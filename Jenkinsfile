
pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building...'
            }
        }
    }

    post {
        success {
            mail to: 'jd.saravanan93@gmail.com',
                 subject: "Build Successful: ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                 body: "The Jenkins job ${env.JOB_NAME} build #${env.BUILD_NUMBER} was successful.\n\nCheck it here: ${env.BUILD_URL}"
        }
        failure {
            mail to: 'jd.saravanan93@gmail.com',
                 subject: "Build Failed: ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                 body: "The Jenkins job ${env.JOB_NAME} build #${env.BUILD_NUMBER} has failed.\n\nCheck it here: ${env.BUILD_URL}"
        }
    }
}

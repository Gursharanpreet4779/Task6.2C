pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    echo 'Building the application...'
                }
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                script {
                    echo 'Running unit and integration tests...'
                }
            }
        }
        stage('Code Analysis') {
            steps {
                script {
                    echo 'Performing code analysis...'
                }
            }
        }
        stage('Security Scan') {
            steps {
                script {
                    echo 'Running security scan...'
                }
            }
        }
        stage('Deploy to Staging') {
            steps {
                script {
                    echo 'Deploying application to staging server...'
                }
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                script {
                    echo 'Running integration tests on staging environment...'
                }
            }
        }
        stage('Deploy to Production') {
            steps {
                script {
                    echo 'Deploying application to production server...'
                }
            }
        }
    }

    post {
        always {
            script {
                echo 'Attempting to send email notification...'
                try {
                    emailext(
                        subject: "Build Status: ${currentBuild.currentResult}",
                        body: "Build #${env.BUILD_NUMBER} finished with status: ${currentBuild.currentResult}.\nCheck logs at ${env.BUILD_URL}",
                        to: "gursharanpreetsinghsidhu38377@gmail.com",
                        attachLog: true
                    )
                    echo 'Email sent successfully!'
                } catch (Exception e) {
                    echo "Email sending failed: ${e}"
                }
            }
        }
    }
}

pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    echo 'Application is starting to build...'
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
                    echo 'Performing security scan...'
                }
            }
        }
        stage('Deploy to Staging') {
            steps {
                script {
                    echo 'Deploying application to staging environment...'
                }
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                script {
                    echo 'Running integration tests on staging...'
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
                echo 'Sending email notification...'
                mail (
                    subject: "Pipeline Notification: ${env.JOB_NAME} - Build #${env.BUILD_NUMBER}",
                    body: "The pipeline has completed. Check details at: ${env.BUILD_URL}",
                    to: 'gursharanpreet4779.be23@chitkara.edu.in'
                )
            }
        }
    }
}

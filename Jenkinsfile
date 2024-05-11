pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo "Building ..." 
                // Add build steps here
            }
            post {
                success {
                    mail to: "zbanda23@gmail.com",
                    subject: "Build Status: Success",
                    body: "Build was successful!",
                    attachLog: true
                }
                failure {
                    mail to: "zbanda23@gmail.com",
                    subject: "Build Status: Failure",
                    body: "Build failed! Please check the logs for details.",
                    attachLog: true
                }
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo "Running unit and integration tests ..."
                // Add test execution steps here
            }
            post {
                success {
                    mail to: "zbanda23@gmail.com",
                    subject: "Unit and Integration Tests: Success",
                    body: "Unit and integration tests passed!",
                    attachLog: true
                }
                failure {
                    mail to: "zbanda23@gmail.com",
                    subject: "Unit and Integration Tests: Failure",
                    body: "Unit and integration tests failed!",
                    attachLog: true
                }
            }
        }
        stage('Code Analysis') {
            steps {
                echo "Performing code analysis ..." 
                // Add code analysis steps here
            }
        }
        stage('Security Scan') {
            steps {
                echo "Performing security scan ..."
                // Add security scan steps here
            }
            post {
                success {
                    mail to: "zbanda23@gmail.com",
                    subject: "Security Scan: Success",
                    body: "Security scan completed successfully!",
                    attachLog: true
                }
                failure {
                    mail to: "zbanda23@gmail.com",
                    subject: "Security Scan: Failure",
                    body: "Security scan failed! Please check the logs for details.",
                    attachLog: true
                }
            }
        }
    }
    
    post {
        success {
            mail to: "zbanda23@gmail.com",
            subject: "Pipeline Status: Success",
            body: "Pipeline completed successfully!",
            attachLog: true
        }
        failure {
            mail to: "zbanda23@gmail.com",
            subject: "Pipeline Status: Failure",
            body: "Pipeline failed! Please check the logs for details.",
            attachLog: true
        }
    }
}

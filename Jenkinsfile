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
                    subject: "Build Status: Successful",
                    body: "Build was successful!",
                    attachLog: true
                }
                failure {
                    mail to: "zbanda23@gmail.com",
                    subject: "Build Status: Failed",
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
                    subject: "Tests Status: Successful",
                    body: "Unit and integration tests were successful!",
                    attachLog: true
                }
                failure {
                    mail to: "zbanda23@gmail.com",
                    subject: "Tests Status: Failed",
                    body: "Unit and integration tests failed! Please check the logs for details.",
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
                    subject: "Security Scan Status: Successful",
                    body: "Security scan was successful!",
                    attachLog: true
                }
                failure {
                    mail to: "zbanda23@gmail.com",
                    subject: "Security Scan Status: Failed",
                    body: "Security scan failed! Please check the logs for details.",
                    attachLog: true
                }
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo "Deploying to staging ..." 
                // Add deployment steps here
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo "Running integration tests on staging ..." 
                // Add integration tests on staging steps here
            }
        }
        stage('Deploy to Production') {
            steps {
                echo "Deploying to production ..." 
                // Add deployment to production steps here
            }
        }
    }
    
    post {
        success {
            mail to: "zbanda23@gmail.com",
            subject: "Pipeline Status: Successful",
            body: "Pipeline completed successfully!",
            attachLog: true
        }
        failure {
            mail to: "zbanda23@gmail.com",
            subject: "Pipeline Status: Failed",
            body: "Pipeline failed! Please check the logs for details.",
            attachLog: true
        }
    }
}

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
                    subject: "Build Status Email",
                    body: "Build was successful!"
                }
                failure {
                    mail to: "zbanda23@gmail.com",
                    subject: "Build Status Email",
                    body: "Build failed! Please check the logs for details."
                }
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo "Running unit and integration tests ..." 
                // Add test execution steps here
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
                    sendSecurityScanNotification('Security Scan', 'success')
                }
                failure {
                    sendSecurityScanNotification('Security Scan', 'failure')
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
            subject: "Pipeline Status Email",
            body: "Pipeline completed successfully!"
        }
        failure {
            mail to: "zbanda23@gmail.com",
            subject: "Pipeline Status Email",
            body: "Pipeline failed! Please check the logs for details."
        }
    }
}

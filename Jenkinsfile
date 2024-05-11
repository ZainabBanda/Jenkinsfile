pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                // Use Maven to build the code
                sh 'mvn clean package'
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                // Run unit tests
                sh 'mvn test'
                // Run integration tests using Selenium
                // (Assuming Selenium is configured and tests are available)
            }
        }
        stage('Code Analysis') {
            steps {
                // Integrate SonarQube for code analysis
                // (Assuming SonarQube is configured)
            }
        }
        stage('Security Scan') {
            steps {
                // Perform security scan using OWASP Dependency-Check
                // (Assuming Dependency-Check is configured)
            }
        }
        stage('Deploy to Staging') {
            steps {
                // Deploy application to staging server using Jenkins SSH plugin
                // (Assuming SSH plugin is configured)
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                // Run integration tests on staging environment using Selenium
                // (Assuming Selenium is configured)
            }
        }
        stage('Deploy to Production') {
            steps {
                // Deploy application to production server using Jenkins SSH plugin
                // (Assuming SSH plugin is configured)
            }
        }
    }
    
    post {
        success {
            // Send email notification for successful build
            emailext body: 'The pipeline has been successfully executed.',
                subject: 'Pipeline Successful',
                to: 'zbanda23@gmail.com'
        }
        failure {
            // Send email notification for failed build
            emailext body: 'The pipeline has failed.',
                subject: 'Pipeline Failed',
                to: 'zbanda23@gmail.com'
        }
    }
}

pipeline {
    agent any
    
    stages {
        stage("Build") {
            steps {
                echo 'Building code using Maven'
                // Add build commands using Maven
            }
        }
        
        stage("Unit and Integration Tests") {
            steps {
                echo 'Unit test for code function'
                echo 'Integration Test working together'
            }
            post {
                success {
                    mail to: "zbanda23@gmail.com",
                    subject: "Unit and Integration test successful.",
                    body: "Unit and Integration tests passed successfully."
                }
                failure {
                    mail to: "zbanda23@gmail.com",
                    subject: "Unit and Integration test failure.",
                    body: "Unit and Integration tests failed. Please try again."
                }
            }
        }
        
        stage("Code Analysis") {
            steps {
                echo 'Performing code analysis using SonarQube'
                // Add commands to run code analysis using SonarQube
            }
        }
        
        stage("Security Scan") {
            steps {
                echo 'Performing security scan'
                // Add commands to perform security scan
            }
            post {
                success {
                    mail to: "zbanda23@gmail.com",
                    subject: "Security scans successful.",
                    body: "Security scans was successful."
                }
                failure {
                    mail to: "zbanda23@gmail.com",
                    subject: "Security scans failure.",
                    body: "Security scans failed."
                }
            }
        }
        
        stage("Deploy to Staging") {
            steps {
                echo 'Deploying to staging'
                
            }
        }
        
        stage("Integration Tests on Staging") {
            steps {
                echo 'Running Integration Tests on Staging environment'
                // Add commands to run integration tests on staging
            }
        }
        
        stage("Deploy to Production") {
            steps {
                echo 'Deploying to Production'
                // Add commands to deploy to production server
            }
        }
    }
    
    post {
        success {
            echo 'Deployment to production successful!'
        }
        failure {
            echo 'Deployment failed!'
        }
    }
}

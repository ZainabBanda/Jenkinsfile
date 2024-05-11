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
            post {
                success {
                    mail to: "zbanda23@gmail.com",
                    subject: "Success: Unit and Integration test successful.",
                    body: "Stage is working.",
                    attachLog: true
                }
                failure {
                    mail to: "zbanda23@gmail.com",
                    subject: "Unsuccess: Unit and Integration test failure.",
                    body: "Stage is not working.",
                    attachLog: true
                }
            }
            }
            post {
                success {
                    emailext(
                        to: "zbanda23@gmail.com",
                        subject: "Test Status Email",
                        body: "Unit and integration tests passed!",
                        attachLog: true
                    )
                }
                failure {
                    emailext(
                        to: "zbanda23@gmail.com",
                        subject: "Test Status Email",
                        body: "Unit and integration tests failed!",
                        attachLog: true
                    )
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
                    subject: "Security scans successful.",
                    body: "Scan is secure.",
                    attachLog: true
                }
                failure {
                    mail to: "zbanda23@gmail.com",
                    subject: "Unsuccess: Security scans failure.",
                    body: "Scan is not secure.",
                    attachLog: true
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

pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                echo 'Building the code ...'
                sh 'mvn clean package'
            }
        }
        
        stage('Unit and Integration Tests') {
            steps {
                echo 'Running unit and integration tests ...'
                // Add commands to run tests
            }
            post {
                success {
                    emailext body: "Unit and Integration tests were successful.",
                             subject: "Unit and Integration Test Success",
                             to: "zbanda23@gmail.com",
                             attachLog: true
                }
                failure {
                    emailext body: "Unit and Integration tests failed. Please check the logs for details.",
                             subject: "Unit and Integration Test Failure",
                             to: "zbanda23@gmail.com",
                             attachLog: true
                }
            }
        }
        
        stage('Code Analysis') {
            steps {
                echo 'Running code analysis ...'
                withSonarQubeEnv('SonarQube') {
                    sh 'mvn sonar:sonar'
                }
            }
        }
        
        stage('Security Scan') {
            steps {
                echo 'Performing security scan ...'
                sh 'dependency-check --scan . --format HTML --out ./'
            }
        }
        
        stage('Deploy to Staging') {
            steps {
                echo 'Deploying to staging server ...'
                sshPublisher(
                    publishers: [sshPublisherDesc(
                        configName: "Staging Server",
                        transfers: [sshTransfer(
                            execCommand: "scripts/deploy.sh",
                            execTimeout: 120
                        )]
                    )]
                )
            }
        }
        
        stage('Integration Tests on Staging') {
            steps {
                echo 'Running integration tests on staging ...'
                // Add commands to run integration tests
            }
        }
        
        stage('Deploy to Production') {
            steps {
                echo 'Deploying to production server ...'
                sshPublisher(
                    publishers: [sshPublisherDesc(
                        configName: "Production Server",
                        transfers: [sshTransfer(
                            execCommand: "scripts/deploy.sh",
                            execTimeout: 120
                        )]
                    )]
                )
            }
        }
    }
    
    post {
        success {
            emailext body: "Pipeline successfully completed.",
                     subject: "Pipeline Success",
                     to: "zbanda23@gmail.com",
                     attachLog: true
        }
        failure {
            emailext body: "Pipeline failed.",
                     subject: "Pipeline Failure",
                     to: "zbanda23@gmail.com",
                     attachLog: true
        }
    }
}

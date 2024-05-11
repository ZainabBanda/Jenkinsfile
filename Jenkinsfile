pipeline{
    agent any
    stages{
        stage('Build'){
            steps{
                echo "Building ..." 
            }
            post{
                success{
                    mail to: "zbanda23@gmail.com",
                    subject: "Build status Email",
                    body: "Build log attached!"  
                }
            }
        }
        stage('Test'){
            steps{
                echo "Testing ..."
            }
        }
        stage('Deploy'){
            steps{
                echo "Deploying ..."
            }
        }
        stage('complete'){
            steps{
                echo "completed ..."
            }
        }
    } 
}

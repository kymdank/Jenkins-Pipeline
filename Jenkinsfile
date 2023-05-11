Pipeline{
    agent any
    environment {
        DIRECTORY_PATH="/home/kymfalzon/SIT223/jdk-20/Jenkinsfile"
        TESTING_ENVIRONMENT="Jenkins"
        PRODUCTION_ENVIRONMENT="Kym"
    }
    stages{
        stage('Build'){
            steps{
                echo "Building code with Maven"
            }        
        }

        stage('Unit and Integration Tests'){
            steps{
                echo "using Selenium, running unit tests to ensure the code functions as expected and running integration tests to ensure the different components of the application work together as expected"
            }
            post{
                success{
                    mail to: "kymfalzon@gmail.com",
                    subject: "Test Status Email",
                    body: "Unit and integration tests was successful"
                }
                Failure{
                    mail to: "kymfalzon@gmail.com",
                    subject: "Test Status Email",
                    body: "Security scan was unsuccessful"
                }
            }
        }

        stage('Code Analysis'){
            steps{
                echo "analysing the code and ensuring it meets industry standards with SonarQube"
            }
        }

        stage('Security Scan'){
            steps{
                echo "performing a security scan on the code using Fortify Static Code Analyzer"
            }
            post{
                success{
                    mail to: "kymfalzon@gmail.com",
                    subject: "Security Scan Status Email",
                    body: "Security scan was successful"
                }
                Failure{
                    mail to: "kymfalzon@gmail.com",
                    subject: "Security Scan Status Email",
                    body: "Security scan was unsuccessful"
                }
            }
        }

        stage('Deploy to Staging'){
            steps{
                echo "deploying the application to staging server, AWS EC2 instance."
            }    
        }  

        stage('Integration Tests on Staging'){
            steps{
                echo "running integration tests on the staging environment to ensure the application functions as expected in a production-like environment."
            }
        }

        stage('Deploy to Production'){
            steps{
                echo "deploying the application to production server AWS EC2 instance"
            }
        }
    }
}
  
  

 

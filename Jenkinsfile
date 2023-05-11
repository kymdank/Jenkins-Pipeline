pipeline{
    agent any
    environment {
        DIRECTORY_PATH="/home/kymfalzon/SIT223/jdk-20/Jenkinsfile"
        TESTING_ENVIRONMENT="Jenkins"
        PRODUCTION_ENVIRONMENT="Kym"
    }
    stages{
        stage('Build'){
            steps{
                echo "Building....."
            }
            post{
                success {
                    mail to: "kymfalzon@gamil.com",
                    subject: "Build Status Email",
                    body: "Build was successful",
                }
            }
        
        }
        stage('Test'){
            steps{
                echo "Unit test" 
                echo "integration test"
            }
        }
        stage('Code Quality Check'){
            steps{
                echo "Check the quality of the code"
            }
        }
        stage('Deploy'){
            steps{
                echo "Deploy the application to $TESTING_ENVIRONMENT"
            }
        }
        stage('Approval'){
            steps{
                retry(2){
                    echo "Approval started. Sleep command in place to simulate manual approval."
                }
                    timeout(time: 3, unit:'SECONDS')
                {
                    sleep 10
                }
            }           
        }
        stage('Depoly to Production'){
            steps{
                echo "Deploy the code to the production environment, $PRODUCTION_ENVIRONMENT"
            }
        }
    }
}
  

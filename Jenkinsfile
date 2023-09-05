pipeline{
    agent any
    stages{
        stage('Build'){
            steps{
                echo "Building ...",
                echo "using the maven tool"
                echo 'mvn clean install'
            }
            post{
                success{
                    echo 'Build successful'
                }
                failure{
                    echo 'Build failed'
                }
           }
        }
        
        stage('Unit and Integration Tests'){
            steps{
                echo "Testing code ..."
            }
        }
        stage('Code Analysis'){
            steps{
                echo "Analysing code..."
            }
        }
        stage('Security Scan'){
            steps{
                echo "Checking code for vulnerabilities"
            }
        }
        stage('Deploy to staging'){
            steps{
                echo "Deploying to application staging"
            }
        }
        stage('Integration tests on staging'){
            steps{
                echo "Running integration tests on staging environment"
            }
        }
        stage('Deploy to Production'){
            steps{
                echo "Deploying to production"
            }
        }
    }
}

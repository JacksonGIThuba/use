pipeline{
    agent any
    stages{
        stage('Build'){
            steps{
                echo "Building ..."
                echo "using maven as the automated tool"
                echo 'mvn clean install'
            }
            post{
                success{
                    emailext(
                        to: "jacksonbouwman12@gmail.com",
                        subject: "build status email logs",
                        body: "this was successfull",
                        attachLog: true, 
                    )
                }
                failure{
                    echo 'Build failed'
                }
           }
        }
        
        stage('Unit and Integration Tests'){
            steps{
                echo "Testing code ..."
                echo "sh 'mvn test' "
            }
            post{
                success{
                    echo 'Testing successful'
                }
                failure{
                    echo 'Testing failed'
                }
           }
        }
        stage('Code Analysis'){
            steps{
                echo "Analysing code using SonarQube"
                echo "sh 'mvn sonar:sonar' "
            }
            post{
                success{
                    echo 'Analysis successful'
                }
                failure{
                    echo 'Analysis failed'
                }
           }
        }
        stage('Security Scan'){
            steps{
                echo "Checking code for vulnerabilities"
                echo "sh 'sudo nmap -sV -O ip addr"
            }
            post{
                success{
                    echo 'Scanning successful'
                }
                failure{
                    echo 'Scanning failed'
                }
           }
        }
        stage('Deploy to staging'){
            steps{
                echo "Deploying to application staging"
                echo "sh './deploy_to_staging.sh' "
            }
            post{
                success{
                    echo 'Deployment successful'
                }
                failure{
                    echo 'Deployment failed'
                }
           }
        }
        stage('Integration tests on staging'){
            steps{
                echo "Running integration tests on staging environment"
                echo "sh './run_staging_integration_tests.sh' "
            }
            post{
                success{
                    echo 'Testing successful'
                }
                failure{
                    echo 'Testing failed'
                }
           }
        }
        stage('Deploy to Production'){
            steps{
                echo "Deploying to production"
                echo "sh './deploy_to_production.sh' "
            }
            post{
                success{
                    echo 'Deployment successful'
                }
                failure{
                    echo 'Deployment failed'
                }
           }
        }
    }
}

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
                echo "sh 'mvn test' "
            }
            post{
                success{
                    emailext(
                        from: "jacksonbouwman12@gmail.com",
                        subject: "Unit and Integration tests status logs",
                        body: "this was successfull",
                        attachLog: true,
                        to: "jacksonbouwman12@gmail.com"
                    )
                }
                failure{
                    emailext(
                        from: "jacksonbouwman12@gmail.com",
                        subject: "Unit and Integration tests status logs",
                        body: "this failed",
                        attachLog: true,
                        to: "jacksonbouwman12@gmail.com"
                    )
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
                    emailext(
                        from: "jacksonbouwman12@gmail.com",
                        subject: "Security Scan status logs",
                        body: "this was successfull",
                        attachLog: true,
                        to: "jacksonbouwman12@gmail.com"
                    )
                }
                failure{
                    emailext(
                        from: "jacksonbouwman12@gmail.com",
                        subject: "Security Scan status logs",
                        body: "this failed",
                        attachLog: true,
                        to: "jacksonbouwman12@gmail.com"
                    )
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
                    emailext(
                        from: "jacksonbouwman12@gmail.com",
                        subject: "Integration tests on staging",
                        body: "this was successfull",
                        attachLog: true,
                        to: "jacksonbouwman12@gmail.com"
                    )
                }
                failure{
                    emailext(
                        from: "jacksonbouwman12@gmail.com",
                        subject: "Integration tests on staging",
                        body: "this failed",
                        attachLog: true,
                        to: "jacksonbouwman12@gmail.com"
                    )
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

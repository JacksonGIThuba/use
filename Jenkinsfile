pipeline{
    agent any
    stages{
        stage('Build'){
            steps{
                echo "building ..."
            }
            post{
                always{
                    mail to: "jacksonbouwman12@gmail.com",
                    subject: "build status email",
                    body: "this worked blud"
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
                echo "deploying ..."
            }
        }
        stage('Complete'){
            steps{
                echo "Completed"
            }
        }
    }
}

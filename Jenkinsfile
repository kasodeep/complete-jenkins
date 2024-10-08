// Declrative Pipeline.
pipeline {
   agent any

   tools {        
      // The tool we specified in the jenkins server.
      maven "Jenkins Maven"
   }

   stages {
      stage('Checkout') {
         steps {
            // Get some code from a GitHub repository
            git 'https://github.com/jenkins-docs/simple-java-maven-app.git'
         }
      }

      stage('Build') {
         steps {            
            bat "mvn clean package"
         }
      }

      stage('Test') {
         steps {            
            bat "mvn test"
         }

         post {
            always {
               junit '**/target/surefire-reports/TEST-*.xml'
            }
         }
      }

      stage('Approval') {
         steps {            
            input "Approve Deployment to Production?"
         }
      }

      stage('Deploy') {
         steps {            
            bat "echo Deployed!"
         }
      }
   }

   post {
      failure{
         bat "echo Failure!!"
         mail to: 'kasodariyadeep@gmail.com',
               subject: "Failed Pipeline: ${env.JOB_NAME} - Build #${env.BUILD_NUMBER}",
               body: "Job '${env.JOB_NAME}' (${env.BUILD_URL}) failed."
      }

      success{
         bat "echo Build and Test Successful!!"
         archiveArtifacts artifacts: '**/target/*.jar', onlyIfSuccessful: true
      }
   }
}

pipeline {
    agent any
    
    environment {
        NAME="Deep"
        AGE=20
        PASS=credentials('PASSWORD')
    }

    stages {
        stage('Build') {
            steps {
                bat '''
                echo Hello
                echo %PASS%
                '''
                // Retries only on failure.
                retry(3) {
                    bat 'echo Trying...'
                }
            }
        }
        
        stage('Testing') {
            steps {
                timeout(time: 5, unit: 'SECONDS') {
                    
                }
            }
        }
    }
}


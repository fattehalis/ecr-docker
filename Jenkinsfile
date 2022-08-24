pipeline {
    agent any
     stages {
       // Building Docker images
    stage('Building image') {
      steps{
        script {
        sh 'aws ecr-public get-login-password --region us-east-1 | docker login --username AWS --password-stdin public.ecr.aws/g8n9i4i6'
         sh 'docker build -t jenkins .'
        }
      }
    }
   
    // Uploading Docker images into AWS ECR
    stage('Pushing to ECR') {
     steps{  
         script {
           sh 'docker tag jenkins:latest public.ecr.aws/g8n9i4i6/jenkins:latest'
           sh 'docker push public.ecr.aws/g8n9i4i6/jenkins:latest'
         }
        }
      }
    }
}

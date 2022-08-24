pipeline {
    agent any
     stages {
       // Building Docker images
    stage('Building image') {
      steps{
        script {
         sh 'docker build -t jenkins-docker-pipeline-repo .'
        }
      }
    }
   
    // Uploading Docker images into AWS ECR
    stage('Pushing to ECR') {
     steps{  
         script {
           sh 'docker tag jenkins-docker-pipeline-repo:latest 078591229396.dkr.ecr.us-east-1.amazonaws.com/jenkins-docker-pipeline-repo:latest'
           sh 'docker push 078591229396.dkr.ecr.us-east-1.amazonaws.com/jenkins-docker-pipeline-repo:latest'
         }
        }
      }
    }
}

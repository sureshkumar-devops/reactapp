pipeline
{
    agent any
    environment
    {
       DOCKERHUB_CREDENTIALS = credentials('lehardocker')
    }
    stages
    {
       stage('Get Code from GitHub')
       {
         steps
         {
           git 'https://github.com/sureshkumar-devops/reactapp.git'
           echo 'Clone Project Completed..'

         }
       }       
       stage('Build Docker Image')
       {
         steps
         {
           sh 'docker Build -t lehardocker/reactapp:$BUILD_NUMBER .'
           echo 'Build Image Completed' 
         }
       }       
     
    }
   
}

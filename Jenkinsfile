pipeline
{
    agent any
    environment
    {
       DOCKERHUB_CREDENTIALS = credentials('lehar-dockerhub-token')
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
      
     
    }
   
}

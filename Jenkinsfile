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
       stage('Build Docker Image')
       {
         steps
         {
           sh 'sudo docker build -t lehardocker/reactapp:$BUILD_NUMBER .'
           echo 'Build Image Completed' 
         }
       }       
       stage('Login to DockerHub Account')
       {
         steps
         {
            sh 'echo $DOCKERHUB_CREDENTIALS_PSW | sudo docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
         }
       }
       stage('Push The Image into DockerHub Account')
       {
         steps
         {
            sh 'docker push lehardocker/reactapp:$BUILD_NUMBER'
         }
       }
    }
    post
    {
      always
      {
        sh 'docker logout'
      }
    }
}

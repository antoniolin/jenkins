pipeline{
  agent {
    dockerfile true
  }
  
  stages{
  
    stage('Checkout resource'){
      steps{
        git 'https://github.com/antoniolin/jenkins.git'
      }
    }
    
    stage('Build Image'){
      steps{
        script{ 
          def customImage = docker.build("my-image:${env.BUILD_ID}")
        }
      }
    }

  }
  

}

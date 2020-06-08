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
          def customImage = docker.build("http-server-test")
        }
      }
    }

  }
  

}

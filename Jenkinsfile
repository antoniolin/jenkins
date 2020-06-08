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
          docker.withRegistry('localhost:5000'){
            def customImage = docker.build("my-image:${env.BUILD_ID}")
            customImage.push()
          }
        }
      }
    }

  }
  

}

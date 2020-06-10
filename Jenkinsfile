pipeline {

  agent {
    dockerfile true
  }

  stages {

    stage('Checkout Source') {
      steps {
        git 'https://github.com/antoniolin/jenkins.git'
      }
    }
    stage('Build Image') {
      steps {
        script {
          echo 'hh'
        }
      }
    }        
    stage('Deploy App') {
      steps {
        script {
          kubernetesDeploy(configs: "nginx-server.yaml", kubeconfigId: "mykubeconfig")
        }
      }
    }

  }

}

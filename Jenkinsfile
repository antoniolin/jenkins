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
          def customImage = docker.build("my-image:${env.BUILD_ID}")
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

pipeline {

  agent {
    kubernetes {
    }
  }

  stages {

    stage('Checkout Source') {
      steps {
        git url:'https://github.com/tinaranich/playjenkins.git', branch:'test-deploy-stage'
      }
    }

    stage('Deploy App') {
      steps {
        script {
          kubernetesDeploy(configs: "nginx.yaml", kubeconfigId: "kube-deploy")
        }
      }
    }

  }

}

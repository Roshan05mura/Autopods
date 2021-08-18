pipeline {

 agent{ label 'kubepod'
        kubernetes {
      	cloud 'kubernetes'
      	defaultContainer 'jnlp'
      }
}

  stages {

    stage('Checkout Source') {
      steps {
        git url:'https://github.com/Roshan05mura/Autopods.git', branch:'test-deploy-stage'
      }
    }

    stage('Deploy App') {
      steps {
        script {
          kubernetesDeploy(configs: "nginx.yaml", kubeconfigId: "mykubeconfig")
        }
      }
    }

  }

}

pipeline {

  agent any

  stages {

    stage('Checkout Source') {
      steps {
        git 'https://github.com/justmeandopensource/playjenkins.git', branch:'topic-k8s-pipeline'
      }
    }

    stage('Deploy App') {
      steps {
        script {
          kubernetesDeploy(configs: "nginx.yaml", kubeconfigId: "kubeconfig")
        }
      }
    }

  }

}

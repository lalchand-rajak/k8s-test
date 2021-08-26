pipeline {

  agent any

  stages {

    stage('Checkout Source') {
      steps {
        git url:'https://github.com/lalchand-rajak/k8s-test.git', branch:'main'
      }
    }

   /* stage('Deploy App') {
      steps {
        script {
          kubernetesDeploy(configs: "nginx.yaml", kubeconfigId: "mykubeconfig")
        }
      }
    }
    */
    stage("deployemt using kubectl"){
      steps{
        sh "kubectl apply -f nginx.yaml"
      }
    
    }

  
  }

}

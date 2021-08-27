pipeline {

  agent any

  stages {

    stage('Checkout Source') {
      steps {
        git url:'https://github.com/lalchand-rajak/k8s-test.git', branch:'main'
      }
    }
    
    
  
    stage('Deploy Kubernetes ') {
      steps{
      /*withKubeCredentials(kubectlCredentials: [[ credentialsId: 'test', serverUrl: 'https://10.210.0.133:6443']]) {
    // some block
    //sh ' kubectl apply -f nginx.yml '
     // kubernetesDeploy(configs: "nginx.yaml",kubeconfigId: "K8s-test")
            }*/
        sshagent(['K8s-test-cluster-1']) {
    // some block
          script{
            sh ' kubectl apply -f nginx.yml '
          }
        }
      }
     
    }
  }
}

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
      sshagent(['K8s-test-cluster-1']) {
         sh ' kubectl apply -f nginx.yml '
    
          }
     
        }
      }
    }
}

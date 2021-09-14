pipeline {

  agent any
  options {
    disableConcurrentBuilds()  //each branch has 1 job running at a time
  }
  stages {

    stage('Checkout Source') {
      steps {
        git url:'https://github.com/lalchand-rajak/k8s-test.git', branch:'main'
      }
    }
    
    
  
    stage('Deploy Kubernetes ') {
      steps{
        withCredentials([kubeconfigFile(credentialsId: 'test-cluster', variable: 'KUBECONFIG')]) {
            // some block
            sh 'kubectl apply -f nginx.yaml'
        }
            
                
              
            }
              
        }
    } 
}
     
    

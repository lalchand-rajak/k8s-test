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
      kubeconfig(credentialsId: 'k8s', serverUrl: 'https://10.210.0.133:6443') {
    // some block
    sh ' kubectl apply -f nginx.yml '
                 
    }
   
      }
     
    }
  }
}

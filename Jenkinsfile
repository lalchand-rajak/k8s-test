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
    
    
  
    stage('Deploy Kubernetes '){
    agent{label 'k8s'}
    
        steps{          
           sh 'kubectl apply -f nginx.yaml'
        }
    post { 
        always { 
            cleanWs()
            }
        }
    }

    
        }
    
    post { 
        always { 
            cleanWs()
            }
        }



}  
    

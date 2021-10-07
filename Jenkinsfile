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
    
    
  
    sshagent(['k8s deploy']) {
      sh "scp -o StrictHostKeyChecking=no nginx.yaml root@10.210.0.133:/root"
  script{
      try{
            sh "ssh root@10.210.0.133 kubectl apply -f nginx.yaml"
      }catch(error){
            sh " ssh root@10.210.0.133 kubectl create -f nginx.yaml"
        }
    
    }
  }
   

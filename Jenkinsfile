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
        sshagent(['k8s-deploy']) {
               //sh ''' ssh root@10.210.0.133 '''
               sh "scp -o StrictHostKeyChecking=no nginx.yaml root@10.210.0.133:/root"
              script{
                  try{
                    sh "ssh root@10.210.0.133 kubectl apply -f ."
                  }catch(error){
                    sh " ssh root@10.210.0.133  kubectl create -f ."
                  }
              }
              
            }
              
          }
        } 
      }
     
    }

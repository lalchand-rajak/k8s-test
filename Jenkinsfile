pipeline {

  agent any

  stages {

    stage('Checkout Source') {
      steps {
        git url:'https://github.com/lalchand-rajak/k8s-test.git', branch:'main'
      }
    }
    
  
    /*stage('Deploy Kubernetes ') {
      steps{
     withKubeConfig(credentialsId: 'test', serverUrl: 'https://10.210.0.133:6443') {
      sh 'kubectl apply -f nginx.yml'
        }
      }
    }*/

    stage("Deploye into k8s"){
      agent {
        kubernetes {
      	  cloud 'kubernetes'
      	//defaultContainer 'jnlp'
      }

      stage('Deploy App') {
      steps {
        script {
          kubernetesDeploy(configs: "nginx.yaml", kubeconfigId: "K8s-test")
         }
    
        }
      }
    }

    
  
   /*stage('Deploy App') {
      steps {
        //script {
        //  kubernetesDeploy(configs: "nginx.yaml", kubeconfigId: "mykubeconfig")
        // }
        //withKubeCredentials(kubectlCredentials: [[ credentialsId: 'K8s-test-cluster', namespace: 'test']]) {
        //sh ' kubectl apply -f nginx.yml '
        // some block
     withKubeConfig(credentialsId: 'K8s-test-cluster',serverUrl: 'https://10.210.0.133:6443') {
     sh 'kubectl apply -f nginx.yml'
        // some block
    }
      }
    }*/
    
    
   /* stage("SSH Into k8s Server") {
      steps{
        def remote = [:]
        remote.name = 'elk-master'
        remote.host = '10.210.0.133'
        remote.user = 'root'
        remote.password = 'Welcome@123'
        remote.allowAnyHosts = true

        stage('Put nginx.yml onto k8smaster') {
            sshPut remote: remote, from: 'nginx.yml', into: '.'
        }

        stage('Deploy spring boot') {
          sshCommand remote: remote, command: "kubectl apply -f nginx.yml"
        }
      }
    }*/
    
  }
  
}


}


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
    stage("SSH Into k8s Server") {
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
    }
    
  }
  
}


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
        withKubeConfig(caCertificate: '''-----BEGIN CERTIFICATE-----
        MIIC5zCCAc+gAwIBAgIBADANBgkqhkiG9w0BAQsFADAVMRMwEQYDVQQDEwprdWJl
        cm5ldGVzMB4XDTIxMDkwMTE1MTM1N1oXDTMxMDgzMDE1MTM1N1owFTETMBEGA1UE
        AxMKa3ViZXJuZXRlczCCASIwDQYJKoZIhvcNAQEBBQADggEPADCCAQoCggEBAKl8
        4BoKqW6lupkovgl6S8n7vhMwsfY8we33uVf7rXQi4xAzzsuW1rIY70o1QsqBD2h2
        a412twtBDSeQOi82Ia4Vffe3ZuP66MF+MMp8SwizX6PQBeJvSFPNVwUvtNHXc8Hn
        2ftBdCqBYQbppzplIOA6HNvlueQhyLInZR21hFBxSnnXo8UamcO0SV0bXlt5Dq0z
        ZnQpZONls4q8CbdRfABc+0w7/rABhH3ufSOayRoBqJenu8xVnO69XbYK0whCeAIw
        y3PnPMoB7gGgPeDGZpz6BXb5mYowx4sWYiqWTG2GMAz7CciMpPDbKKJz5OywkhqS
        B76fXbzBhKrwu+GCxLsCAwEAAaNCMEAwDgYDVR0PAQH/BAQDAgKkMA8GA1UdEwEB
        /wQFMAMBAf8wHQYDVR0OBBYEFHnjgVkPLpTMhvxyDqQm4uQPPZGDMA0GCSqGSIb3
        DQEBCwUAA4IBAQAoXvOpPQfLTybnH25d7UwwAJAxYFYvdu75HRYA6Pu7pGP0RG6O
        S9SRy2Glc1tbEBgisIkHaijxflcxU5DkIBR8xZs61FSOgObtvBCM7/I3tLtkplYY
        o+p3Pax3MWMe/7lgxmAfttMsNL3ETPId2HP6YwEV9HGvvf74TGxXqCqQMgQXiICd
        EhGFERseEGXZUNkwD7dZ0S0V1/VULu3oie89f2EovOzzD6A25LfHRtd0inGAx5a1
        lO6932w209yKBgj9Fl5FecfHFvPglOfxBR9I31Y8AZKQBRs22DjiWiHC+BVAfWDW
        y+LjT7NIG3kMvplf4eze81fuyeLnMA+yEThb
        -----END CERTIFICATE-----''', clusterName: 'test', contextName: '', credentialsId: 'k8s-test_cluster', namespace: 'default', serverUrl: ' https://10.210.0.133:6443') {
            sh 'kubectl apply -f nginx.yaml'
        }
            }
              
        }
    }
} 

     
    

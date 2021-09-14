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
        withKubeConfig(caCertificate: ''' LS0tLS1CRUdJTiBDRVJUSUZJQ0FURS0tLS0tCk1JSUM1ekNDQWMrZ0F3SUJBZ0lCQURBTkJna3Foa2lHOXcwQkFRc0ZBREFWTVJNd0VRWURWUVFERXdwcmRXSmwKY201bGRHVnpNQjRYRFRJeE1Ea3dNVEUxTVRNMU4xb1hEVE14TURnek1ERTFNVE0xTjFvd0ZURVRNQkVHQTFVRQpBeE1LYTNWaVpYSnVaWFJsY3pDQ0FTSXdEUVlKS29aSWh2Y05BUUVCQlFBRGdnRVBBRENDQVFvQ2dnRUJBS2w4CjRCb0txVzZsdXBrb3ZnbDZTOG43dmhNd3NmWTh3ZTMzdVZmN3JYUWk0eEF6enN1VzFySVk3MG8xUXNxQkQyaDIKYTQxMnR3dEJEU2VRT2k4MklhNFZmZmUzWnVQNjZNRitNTXA4U3dpelg2UFFCZUp2U0ZQTlZ3VXZ0TkhYYzhIbgoyZnRCZENxQllRYnBwenBsSU9BNkhOdmx1ZVFoeUxJblpSMjFoRkJ4U25uWG84VWFtY08wU1YwYlhsdDVEcTB6ClpuUXBaT05sczRxOENiZFJmQUJjKzB3Ny9yQUJoSDN1ZlNPYXlSb0JxSmVudTh4Vm5PNjlYYllLMHdoQ2VBSXcKeTNQblBNb0I3Z0dnUGVER1pwejZCWGI1bVlvd3g0c1dZaXFXVEcyR01BejdDY2lNcFBEYktLSno1T3l3a2hxUwpCNzZmWGJ6QmhLcnd1K0dDeExzQ0F3RUFBYU5DTUVBd0RnWURWUjBQQVFIL0JBUURBZ0trTUE4R0ExVWRFd0VCCi93UUZNQU1CQWY4d0hRWURWUjBPQkJZRUZIbmpnVmtQTHBUTWh2eHlEcVFtNHVRUFBaR0RNQTBHQ1NxR1NJYjMKRFFFQkN3VUFBNElCQVFBb1h2T3BQUWZMVHlibkgyNWQ3VXd3QUpBeFlGWXZkdTc1SFJZQTZQdTdwR1AwUkc2TwpTOVNSeTJHbGMxdGJFQmdpc0lrSGFpanhmbGN4VTVEa0lCUjh4WnM2MUZTT2dPYnR2QkNNNy9JM3RMdGtwbFlZCm8rcDNQYXgzTVdNZS83bGd4bUFmdHRNc05MM0VUUElkMkhQNll3RVY5SEd2dmY3NFRHeFhxQ3FRTWdRWGlJQ2QKRWhHRkVSc2VFR1haVU5rd0Q3ZFowUzBWMS9WVUx1M29pZTg5ZjJFb3ZPenpENkEyNUxmSFJ0ZDBpbkdBeDVhMQpsTzY5MzJ3MjA5eUtCZ2o5Rmw1RmVjZkhGdlBnbE9meEJSOUkzMVk4QVpLUUJSczIyRGppV2lIQytCVkFmV0RXCnkrTGpUN05JRzNrTXZwbGY0ZXplODFmdXllTG5NQSt5RVRoYgotLS0tLUVORCBDRVJUSUZJQ0FURS0tLS0tCg=='''
, credentialsId: 'k8s-test_cluster',  serverUrl: ' https://10.210.0.133:6443') {
    sh 'kubectl apply -f nginx.yaml'
}
            sh 'kubectl apply -f nginx.yaml'
        }
            
                
              
            }
              
        }
    } 
}
     
    

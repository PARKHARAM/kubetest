  pipeline {
    agent any
    tools {
        terraform 'Terraform14'

    }
    stages { 
        stage('kubectl yaml') {
        steps {
          withCredentials([file(credentialsId: 'gketest', variable: 'GC_KEY')]) {
            sh 'gcloud auth activate-service-account --key-file=${GC_KEY}'
    
            
                 }
          
          sh ("kubectl get nodes") 
          sh ("kubectl apply -f rbac.yaml")
          
        }
      } 

    }
     
  }

  pipeline {
    agent any
    tools {
        terraform 'Terraform14'

    }
    stages { 
        stage('kubectl yaml') {
        steps {
          
          
          sh ("kubectl get nodes") 
          sh ("kubectl apply -f rbac.yaml")
          
        }
      } 

    }
     
  }

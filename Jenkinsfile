  pipeline {
    agent any
    tools {
        terraform 'Terraform14'

    }
    stages {  

    }
     stage('kubectl yaml') {
        steps {
          withCredentials([file(credentialsId: 'gke-test', variable: 'GC_KEY')]) {
            sh 'gcloud auth activate-service-account --key-file=${GC_KEY}'
    
            
                 }
          
          sh ("kubectl get nodes") 
          sh ("kubectl apply -f https://download.elastic.co/downloads/eck/1.0.1/all-in-one.yaml")
          sh ("kubectl  apply -f eck.yaml") 
          sh ("kubectl  apply -f nginx.yaml") 
        }
      }
  }

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
            sh ("gcloud container clusters get-credentials eloquent-marker-338005-gke --region asia-northeast3 --project eloquent-marker-338005")

            sh ("/usr/local/bin/kubectl apply -f nginx.yaml")
            sh ("/usr/local/bin/kubectl apply -f nginx-service.yaml")

            
                 }
          

          
        }
      } 

    }
     
  }

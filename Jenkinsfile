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
            sh ("gcloud container clusters get-credentials pjt-an3-gketest-dev-gke --region asia-northeast1 --project pjt-an3-gketest-dev")
            sh ("kubectl apply -f rbac.yaml")
            
                 }
          

          
        }
      } 

    }
     
  }

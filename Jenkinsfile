pipeline{

    agent any
    
    environment {
    DOCKERHUB_USERNAME = "anuragjoshi01"
    APP_NAME = "gitops-argo-app"
    IMAGE_TAG = "${BUILD_NUMBER}"
    IMAGE_NAME = "${DOCKERHUB_USERNAME}" + "/" + "{APP_NAME}"
    REGISTERY_CREDS = 'dockerhub'
   }
    
   
   stages{
    stage("cleanup workspace"){
        steps{
            script{
                cleanWs()
            }
        }
    }
    stage("git checkout from SCM"){
        steps{
            script{
                git credeantialsId: 'github',
                url: 'https://github.com/anuragjos/gitops_argocd_project.git',
                branch: 'main'
            }
        }
    }
   }
}


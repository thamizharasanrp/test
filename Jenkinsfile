pipeline {
    agent any 
   // environment {
     //           CREDS = credentials('dokube')
       //     }
    stages {
        stage(getpods) {
            steps {
                script {
                    withKubeConfig([credentialsId: 'dokube']) {
                     sh 'helm repo add my-repo https://charts.bitnami.com/bitnami'
                     sh 'helm repo update'
                     sh 'helm upgrade --install my-release my-repo/nginx'  
                     sh 'helm uninstall my-release'   
                        
                    //sh 'kubectl delete -f my-kubernetes-directory'
                
                //sh 'mkdir -p  ~/.kube/'
                //sh 'cat "${CREDS}" > ~/.kube/config'
                //sh 'kubectl apply -f deployment.yml'
                sleep 15
                sh 'kubectl get pods,svc'
                 }       
               }         
            }
        }
    }  
}

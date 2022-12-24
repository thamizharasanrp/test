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
                    //sh 'kubectl apply -f my-kubernetes-directory'
                
                //sh 'mkdir -p  ~/.kube/'
                //sh 'cat "${CREDS}" > ~/.kube/config'
                sh 'kubectl apply -f deployment.yml'
                sleep 15
                sh 'kubectl get pods'
                 }       
               }         
            }
        }
    }  
}

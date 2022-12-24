pipeline {
    agent any 
    environment {
                CREDS = credentials('dokube')
            }
    stages {
        stage(getpods) {
            steps {
                
                sh 'mkdir -p  ./kube/'
                sh 'cat CREDS > ./kube/config'
                #sh 'kubectl --kubeconfig="${CREDS}" get pods'
                sh 'kubectl apply -f deployment.yml'
                #sh 'kubectl --kubeconfig="${CREDS}" delete -f service.yml'
                sleep 15
                sh 'kubectl get pods'
            }
        }
    }  
}

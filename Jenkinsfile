pipeline {
    agent any 
    environment {
                CREDS = credentials('dokube')
            }
    stages {
        stage(getpods) {
            steps {
                
                sh 'mkdir -p  ~/.kube/'
                sh 'cat CREDS > ~/.kube/config'
                sh 'kubectl apply -f deployment.yml'
                sleep 15
                sh 'kubectl get pods'
            }
        }
    }  
}

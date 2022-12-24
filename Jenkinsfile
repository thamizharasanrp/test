pipeline {
    agent any 
    environment {
                CREDS = credentials('dokube')
            }
    stages {
        stage(getpods) {
            steps {
                sh 'kubectl --kubeconfig="${CREDS}" get pods'
                sh 'kubectl --kubeconfig="${CREDS}" apply -f deployment.yml'
                sh 'kubectl --kubeconfig="${CREDS}" apply -f service.yml'
                sleep 60
                sh 'kubectl --kubeconfig="${CREDS}" get pods'
            }
        }
    }  
}

pipeline {
    agent any 
    environment {
                CREDS = credentials('dokube')
            }
    stages {
        stage(getpods) {
            steps {
                sh 'kubectl --kubeconfig="${CREDS}" get pods'
                sh 'kubectl --kubeconfig="${CREDS}" delete -f deployment.yml'
                sh 'kubectl --kubeconfig="${CREDS}" delete -f service.yml'
                sleep 15
                sh 'kubectl --kubeconfig="${CREDS}" get pods'
            }
        }
    }  
}

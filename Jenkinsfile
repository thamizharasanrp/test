pipeline {
    agent any 
    environment {
                CREDS = credentials('dokube')
            }
    stages {
        stage(getpods) {
            steps {
                sh 'kubectl --kubeconfig="${CREDS}" get pods'
            }
        }
    }  
}

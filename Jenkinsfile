pipeline {
    agent any

    stages {
        stage('Check K8S') {
            steps {
                sh 'kubectl get all --namespace flask-datta-able'
                sh 'kubectl get all --namespace projectcontour'
            }
        }
        stage('Flask deploy'){
            steps{
                sh 'kubectl apply -f flask-deployment.yaml'
            }
        }
    }
}

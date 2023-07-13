pipeline {
    agent any

    stages {
        stage('Flask deploy'){
            steps{
                sh 'kubectl apply -f flask-deployment.yaml'
            }
        }
        stage('Check K8S') {
            steps {
                sh 'k get all --all-namespaces -o wide'
            }
        }
    }
}

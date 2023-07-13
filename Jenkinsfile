pipeline {
    agent any

    stages {
        stage('Build Image'){
            steps{
                sh "docker build -t flask-frontend:${params.flask_version} ."      
            }
        }
        stage('Flask deploy'){
            steps{
                sh 'kubectl apply -f flask-deployment.yaml'
            }
        }
        stage('Check K8S') {
            steps {
                sh 'kubectl get all --namespace flask-space'
            }
        }
    }
}

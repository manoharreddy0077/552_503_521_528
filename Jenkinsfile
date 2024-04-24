pipeline {
    agent any
    stages {
        stage('Build Docker Images') {
            steps {
                script {
                    bat 'docker build -t pes1ug21cs503/frontend ./frontend'
                    bat 'docker build -t pes1ug21cs503/auth ./authenticate'
                    bat 'docker build -t pes1ug21cs503/cart ./cart'
                    bat 'docker build -t pes1ug21cs503/items ./items'
                    bat 'docker build -t pes1ug21cs503/order ./order'
                }
            }
        }
        stage('Deploy') {
            steps {
                script {
                    bat 'kubectl delete deployments --all'
                    bat 'kubectl delete services --all'
                    bat 'kubectl apply -f ./k8s/'
                }
            }
        }
    }
}

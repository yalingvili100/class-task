pipeline {
    agent any
    
    stages {
        stage('Checkout Code') {
            steps {
                git branch: 'main', url: 'https://github.com/yalingvili100/class-task.git'
            }
        }
        
        stage('Docker Build+tag') {
            steps {
                sh 'docker build -t yalingvili/flask-hello-world:v1 .'
            }
        }
        
        stage('Docker Push') {
            steps {
                sh 'docker login -u yalingvili -p 1Q2w3e4r1'
                sh 'docker push yalingvili/flask-hello-world:v1'
            }
        }
        stage('deploy'){
            steps{
                sh 'kubectl apply -f deployment.yaml'
            }
        }
    }
}

pipeline{
    agent any
    stages {
        stage('Build Docker Image') {
            steps {
                sh "echo staring build the image"
                sh 'docker build -t 219053493160.dkr.ecr.us-east-1.amazonaws.com/eks:latest .'
            }
        }
    stage('Deploy Docker Image') {
            steps {
                sh "echo staring deploy the image"
                sh 'aws ecr get-login-password --region us-east-1 | docker login --username AWS --password-stdin 219053493160.dkr.ecr.us-east-1.amazonaws.com'
                sh 'docker push 219053493160.dkr.ecr.us-east-1.amazonaws.com/eks:latest'
            }
        }
    }     
}

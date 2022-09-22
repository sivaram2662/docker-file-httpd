pipeline {
    agent any

    stages {
        stage('checkout') {
            steps {
               git branch: 'main', url: 'git@github.com:sivaram2662/terraform-app.git'
            }
        }
         stage('login') {
            steps {
               sh "aws ecr get-login-password --region ap-south-1 | sudo docker login --username AWS --password-stdin 101275806917.dkr.ecr.ap-south-1.amazonaws.com"
            }
        }
        stage('build ') {
            steps {
               sh "sudo docker build -t 101275806917.dkr.ecr.ap-south-1.amazonaws.com/docker-ecr:latest ."
            }
        }
        stage('push') {
            steps {
               sh " sudo docker push 101275806917.dkr.ecr.ap-south-1.amazonaws.com/docker-ecr:latest"
        }

    }
    
}

}
pipeline {
    agent any

    stages {
        stage('aws cli') {
            steps {
                sh "sudo aws ecr get-login-password --region ap-south-1 | docker login --username AWS --password-stdin 101275806917.dkr.ecr.ap-south-1.amazonaws.com"
            }
        }
         stage('build to docker') {
            steps {
               sh "sudo docker build -t docker-ecr ."
            }
        }
        stage('build to tag') {
            steps {
               sh "sudo docker tag docker-ecr:latest 101275806917.dkr.ecr.ap-south-1.amazonaws.com/docker-ecr:latest"
            }
        }stage('build to push') {
            steps {
               sh " sudo docker push 101275806917.dkr.ecr.ap-south-1.amazonaws.com/docker-ecr:latest"
        }

    }
    
}

}
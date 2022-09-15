pipeline {
    agent any

    stages {
        stage('ci') {
            steps {
            sh'zip -r html-helloworld-$BUILD_NUMBER.zip *'
            sh'aws s3 cp html-helloworld-$BUILD_NUMBER.zip s3://artifactory-cicd-siva/'
            }
        }
         stage('ci') {
            steps {
             sh'rm -fr *'
             sh'aws s3 cp s3://artifactory-cicd-siva/html-helloworld-$PKG.zip .'
             sh'unzip html-helloworld-$PKG.zip'
             sh'scp index.html root@172.31.36.60:/var/www/html/'
            }
        }
    }
    
}

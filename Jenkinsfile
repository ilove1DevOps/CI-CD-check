pipeline {
    agent any
    
    environment {
        DOCKERHUB_CREDENTIALS = credentials('DockerHub_cred')
    }
    
    stages {
        stage('Build') {
            steps {
                withCredentials([string(credentialsId: 'DockerhubPassword', variable: 'Docker_Hub_piyushdhir121')]) {
                    // Your build steps here
                    sh 'docker login -u $DOCKERHUB_USERNAME -p $DOCKERHUB_PASSWORD'
                    sh 'docker build -t your-image .'
                }
            }
        }
    }
}

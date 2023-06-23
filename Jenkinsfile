pipeline {
    agent any
    
    environment {
        DOCKERHUB_CREDENTIALS = credentials('DockerHub_cred')
    }
    
    stages {
        stage('Build') {
            steps {
                withCredentials([usernamePassword(credentialsId: 'DockerHub_cred', usernameVariable: 'DOCKERHUB_USERNAME', passwordVariable: 'DOCKERHUB_PASSWORD')]) {
                    // Your build steps here
                    sh 'docker login -u $DOCKERHUB_USERNAME -p $DOCKERHUB_PASSWORD'
                    sh 'docker build -t your-image .'
                }
            }
        }
    }
}

pipeline {
    agent any
    
    environment {
        DOCKERHUB_CREDENTIALS = credentials('Docker_Hub_piyushdhir121')
    }
    
    stages {
        stage('Build') {
            steps {
                withCredentials([usernamePassword(credentialsId: 'Docker_Hub_piyushdhir121', usernameVariable: 'DOCKERHUB_USERNAME', passwordVariable: 'DOCKERHUB_PASSWORD')]) {
                    // Your build steps here
                    sh 'docker login -u $DOCKERHUB_USERNAME -p $DOCKERHUB_PASSWORD'
                    sh 'docker build -t your-image .'
                }
            }
        }
    }
}

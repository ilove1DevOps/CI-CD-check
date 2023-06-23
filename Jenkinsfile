pipeline {
    agent any
    
    environment {
        DOCKERHUB_CREDENTIALS = credentials('DockerHub_cred')
    }
    
    stages {
        stage('Build') {
            steps {
                
                    // Your build steps here
                    sh 'docker build -t your-image .'
                
            }
        }
       
        
    }
}

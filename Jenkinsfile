pipeline {
    agent any    
    stages {
        stage('Build') {
            steps {
                  sh 'docker build -t your-image .'
                
            }
        }
        stage ('push to docker hub'){
            steps{
                withCredentials([string(credentialsId: 'Docker_Hub_piyushdhir121', variable: 'DockerHub_cred')]) {
    

                //sh 'docker login -u piyushdhir121'
                sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'                		
	            echo 'Login Completed' 
                }
            }
    }
}
}

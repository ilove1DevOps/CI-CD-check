pipeline {
    agent any    
    stages {
        stage('Build') {
            steps {
                  sh 'docker build -t your-image .'
                
            }
        }
        stage ('Login to docker hub'){
            steps{
                withCredentials([string(credentialsId: 'Docker_Hub_piyushdhir121', variable: 'DockerHub_cred')]) {
    

                sh 'docker login -u piyushdhir121 -p ${DockerHub_cred}'                		
	        echo 'Login Completed' 
                }
            }
    	}
	stage  ('push Completed'){
		steps{
			sh 'docker push piyushdhir121/your-image:e1 '
			echo 'pushed to docker hub check the docker hub'
		}
	    }
        }
}

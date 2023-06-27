# CI-CD-check
1. Setup Git-hub repo and push the source code.
2. Add ```webhook``` in github use the jenkins url (```https//: IP :8080```).
3. Create Pipeline on jenkins.
4. Go to the ```build triggers``` on Jenkins then enable the ```github hook trigger for git SCM```
5. Go to the ```pipeline``` section and then go in Defination and select ```Pipeline script from SCM```
6. Go to the ```SCM``` then select ```git```
7. Add the GitHub repo url  and type the branch ```main```.
8. Save it.
9. Go to Manage jenkins then go to the credentials thn go to global credentials.
10. Now create the Credentials then select ```kind``` as ```secret text```.
11. Now for secret section, open the ```docker hub``` and go to the ```account setting``` then ```security``` then add token then copy the ```password prompt```.
12. Add the password of access token to the secret as in 10th point.
13. Create the ID name of choice. (```Docker_Hub_piyushdhir121```).
14. Goto the ```pipeline syntax``` then go to the ```snippet generator```.
15. Goto the ```sample step``` select the ```withCredentials : Bind credentials to variables```
16. go to the Binding section and select ```secret text```
17. name the variable (```DockerHub_cred```), selet the credentials that created.
18. Click on generate pipeline script and add the output to the jenkins file.
19. ```pipeline
    {
    agent any    
    stages {
        stage('Build') {
            steps {
                sh 'docker build -t your-image:e1 .'
            }
        }
        stage('Login to Docker Hub') {
            steps {
                withCredentials([string(credentialsId: 'Docker_Hub_piyushdhir121', variable: 'DockerHub_cred')]) {
                    sh "docker login -u piyushdhir121 -p '${DockerHub_cred}'"
                    echo 'Login Completed'
                }
            }
        }
        stage('Push to Docker Hub') {
            steps {
                sh 'docker tag your-image:e1 piyushdhir121/your-image:e1'
                sh 'docker push piyushdhir121/your-image:e1'
                echo 'Pushed to Docker Hub. Check Docker Hub for the image.'
            }
        }
    }
}```

20. Webhook issue install ```ngrok``` this will take the port of your local host and make it live access over the internet.
21. login to ngrok , install the package for MAC os and then ```./ngrok```, then use ```sudo mv ngrok /usr/local/bin/``` to make ngrok work.
22. verify it using ```ngrok --version```.





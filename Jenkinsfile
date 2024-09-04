pipeline {
    agent any 
    stages {
        stage('Clone the repo') {
            steps {
                echo 'clone the repo'
                sh 'rm -fr html'
                sh 'git clone https://github.com/Chanikyakodati/jenkinswebapp.git'
            }  
        }  
        stage('push repo to remote host ') {
            steps {
                echo 'connect to remote host and pull down the latest version'
                sh 'ssh -o StrictHostKeyChecking=no -i /home/ubuntu/chanikyausa.pem ubuntu@44.212.39.110 sudo git -C /var/www/html pull'
            }
        } 
        stage('Check website is up') {
            steps {
                echo 'Check website is up'
                sh 'curl -Is 44.212.39.110 | head -n 1'
            }
        }
    }
}

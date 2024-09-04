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
                sh 'ssh -o StrictHostKeyChecking=no -i /var/lib/jenkins/chanikyausa.pem ubuntu@ec2-44-212-39-110.compute-1.amazonaws.com sudo git -C /var/www/html pull'
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

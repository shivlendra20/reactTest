pipeline {
    agent any
    tools {
        nodejs 'node16'
    } 
    stages {
       stage('StatusCheck'){
        sh 'systemctl status apache2'
       } 

       stage('Dependencies'){
        sh 'npm install'    
       }
       
       stage('Build'){
        sh 'npm run build'
       }

       stage('Deploy'){
        sh 'sudo mv build/* /var/www/html'
       }
    }
}


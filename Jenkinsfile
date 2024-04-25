pipeline {
    agent any
    tools {
        nodejs 'node16'
    } 
    stages {
       stage('StatusCheck'){
        steps{
         sh 'systemctl status apache2'

        }
       }
        
       stage('Node16'){
        steps{
            sh 'nvm install v16.20.2'
        }
       }

       stage('Dependencies'){
        steps{
            sh 'npm install' 
        }
           
       }
       
       stage('Build'){
        steps{
            sh 'npm run build'
        }
       }

       stage('Deploy'){
        steps{
            sh 'sudo cp build/* /var/www/html'
        }
        
       }
    }
}


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
        
       stage('Clean npm Cache') {
        steps {
        sh 'npm cache clean --force'
        }
       }


       stage('Update npm') {
        steps {
         sh 'npm install -g npm@latest'
         }
       }


       stage('Dependencies'){
        steps{
            sh 'npm install --verbose' 
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


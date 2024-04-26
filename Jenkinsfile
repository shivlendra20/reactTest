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

 /*      stage('Purging'){
        steps{
            sh 'rm -rf node_modules build'
        }
       } 
*/
       stage('Dependencies'){
        steps{
            sh 'node -v'
            sh 'npm i' 
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
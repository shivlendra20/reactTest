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
        stage('NodeStatus'){
            steps{
                sh 'sudo node -v'
                sh 'sudo npm -v'
            }
        } 

       stage('Dependencies'){
        steps{
            sh 'sudo npm install' 
        }
           
       }
       
       stage('Build'){
        steps{
            sh 'sudo npm run build'
        }
       }

       stage('Deploy'){
        steps{
            sh 'sudo cp build/* /var/www/html'
        }
        
       }
    }
}


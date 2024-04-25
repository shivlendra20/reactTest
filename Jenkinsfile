pipeline {
    options {
        buildDiscarder(logRotator(numToKeepStr: '10'))
        disableConcurrentBuilds()
    }

    agent any
    tools {
        nodejs 'node16'
    } 

    stages {
        stage('Preparation') {
            steps {
                cleanWs() // Clean workspace before the build
            }
        }
        // Other stages
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
            sh 'npm ci' 
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
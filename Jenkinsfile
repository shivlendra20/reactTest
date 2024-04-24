pipeline {
    agent any
    tools {
        nodejs 'node16'
    } 
    
    
    stages {


        stage('Deploy'){
            steps {
                sh 'pm2 start --name react_test npm -- start'
            }
        }    
    }
}


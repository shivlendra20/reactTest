pipeline {
    agent any
    stages {
        tools {
        nodejs 'node16'
        } 

        stage('Deploy'){
            steps {
                sh 'pm2 start --name react_test npm -- start'
            }
        }    
    }
}


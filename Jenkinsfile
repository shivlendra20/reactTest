pipeline {
    agent any
    stages {

        stage('Deploy'){
            steps {
                sh 'pm2 start --name react_test npm -- start'
            }
        }    
    }
}


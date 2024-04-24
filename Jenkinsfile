pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'npm run build'
            }
        }
        stage('Deploy'){
            steps {
                sh 'pm2 start --name react_test npm -- start'
            }
        }    
    }
}


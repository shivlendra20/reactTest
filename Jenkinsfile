pipeline {
    agent any
    tools {
        nodejs 'node16'
    } 
    stages {
        stage('StatusCheck') {
            steps {
                sh 'systemctl status apache2'
            }
        }
        stage('NodeStatus') {
            steps {
                sh 'node -v'
                sh 'npm install -g npm@8.19.4'
                sh 'npm -v'
            }
        } 
        stage('Dependencies') {
            steps {
                sh 'npm install' 
            }
        }
        stage('Build') {
            steps {
                sh 'npm run build'
            }
        }
        stage('Deploy') {
            steps {
                sh 'cp build/* /var/www/html'
            }
        }
    }
}

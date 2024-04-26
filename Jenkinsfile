pipeline {
    agent {
        label 'node16'
    }
    
    stages {
        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }
        
        stage('Build Project') {
            steps {
                sh 'npm run build'
            }
        }
        
        stage('Deploy to Server') {
            steps {
                sh 'cp -r build/* /var/www/html'
            }
        }
    }
}

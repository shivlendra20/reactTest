pipeline {
    agent any
    stages {
        stage('Setup Node.js') {
            steps {
                // Load NVM
                sh '''
                export NVM_DIR="$HOME/.nvm"
                [ -s "$NVM_DIR/nvm.sh" ] && . "$NVM_DIR/nvm.sh"
                nvm install 16  # Install Node.js version 16
                nvm use 16      # Use Node.js version 16
                '''
            }
        }
        stage('StatusCheck') {
            steps {
                sh 'systemctl status apache2'
            }
        }
        stage('NodeStatus') {
            steps {
                sh 'node -v'
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
                sh 'cp -r build/* /var/www/html'  // Recursive copy for directories
            }
        }
    }
}

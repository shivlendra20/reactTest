pipeline {
    agent any

    stages {
        stage('NodeStatus') {
            steps {
                script {
                    def nodeHome = tool name: 'node16', type: 'hudson.plugins.nodejs.tools.NodeJSInstallation'
                    env.PATH = "${nodeHome}/bin:${env.PATH}"
                    sh 'node -v'
                    sh 'npm -v'
                }
            }
        }
 
        stage('StatusCheck') {
            steps {
                sh 'systemctl status apache2'
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

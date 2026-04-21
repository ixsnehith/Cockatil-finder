pipeline {
    agent any
    tools {
        nodejs 'Node-22.5.1' 
    }
    
    environment {
        NGINX_WEB_ROOT = 'C:\\nginx\\nginx-1.29.8\\html' 
    }
    
    stages {
      
        stage('Install Node Dependencies') {
            steps {
                bat 'npm install'
            }
        }
        
        stage('Build Application') {
            steps {
                bat 'npm run build'
            }
        }
        
        stage('Deploy to Nginx') {
            steps {
                // Copies the built React files into your local Windows Nginx directory
                bat 'xcopy dist\\* "%NGINX_WEB_ROOT%\\" /E /Y'
            }
        }
    }
}

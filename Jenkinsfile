pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {
                git branch: 'main', url: 'https://github.com/Satishganiyada/my-react-application.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                // 
                 sh '''
                    rm -rf node_modules package-lock.json
                    npm cache clean --force
                    npm install
                '''
            }
        }

        stage('Build') {
            steps {
                sh 'npm run build'
            }
        }
        stage('cleanup') {
            steps {
                sh 'sudo systemctl stop nginx'
                sh 'sudo rm -rf  /var/www/html/*'
                sh 'sudo cp -r build/*  /var/www/html/.'
                sh 'sudo systemctl start nginx'
            }    
        }
    }
}


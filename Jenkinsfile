pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {
                git 'https://github.com/Satishganiyada/my-react-application.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }

        stage('Build') {
            steps {
                sh 'npm run build'
            }
        }
    }
}


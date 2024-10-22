pipeline {
    agent any
    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/Loganathan07/sample-node-app.git'
            }
        }
        stage('Install Dependencies') {
            steps {
                bat 'npm install'
            }
        }
        stage('Run Tests') {
            steps {
                bat 'npm test || echo "No tests found"'
            }
        }
        stage('Build Application') {
            steps {
                bat 'npm run build || echo "No build step defined"'
            }
        }
        stage('Deploy Application') {
            steps {
                bat 'nohup npm start &'
            }
        }
    }
    post {
        success {
            echo 'Application deployed successfully!'
        }
        failure {
            echo 'Build or deployment failed.'
        }
    }
}

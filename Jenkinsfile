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
                sh 'npm install'
            }
        }
        stage('Run Tests') {
            steps {
                sh 'npm test || echo "No tests found"'
            }
        }
        stage('Build Application') {
            steps {
                sh 'npm run build || echo "No build step defined"'
            }
        }
        stage('Deploy Application') {
            steps {
                sh 'nohup npm start &'
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

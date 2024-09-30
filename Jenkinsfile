pipeline {
    agent any
    stages {
        stage('Clone Repository') {
            steps {
                // Clone your Git repository
                git branch: 'main', url: 'https://github.com/jasonkiptoo/test-jenkins.git'

                // git 'https://github.com/yourusername/your-flask-app.git'
            }
        }
        stage('Install Dependencies') {
            steps {
                // Install dependencies (assuming you have a requirements.txt file)
                sh 'pip install -r requirements.txt'
            }
        }
        stage('Run Tests') {
            steps {
                // Run your tests
                sh 'python run_tests.py'
            }
        }
        stage('Build') {
            steps {
                // Optional: Run any build steps
                echo 'Building the application...'
            }
        }
        stage('Deploy') {
            steps {
                // Optional: Deploy steps (e.g., copy files, restart server)
                echo 'Deploying the application...'
            }
        }
    }
    post {
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}

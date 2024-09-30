pipeline {
    agent any

    environment {
        VENV = 'venv'  // Virtual environment directory
    }

    stages {
        stage('Clone Repository') {
            steps {
                // Clone the repository
                git branch: 'main', url: 'https://github.com/jasonkiptoo/test-jenkins.git'
            }
        }

        stage('Setup Virtual Environment') {
            steps {
                script {
                    sh '''
                    python3 -m venv venv
                    . venv/bin/activate
                    pip install --upgrade pip
                    pip install -r requirements.txt
                    '''
                }
            }
        }
        stage('Run Unit Tests') {
            steps {
                // Run the unit tests within the virtual environment
                sh '''
                . ${VENV}/bin/activate
                python -m unittest discover tests
                '''
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying the Flask application...'
                // Placeholder for deployment steps
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed. Check the logs.'
        }
    }
}

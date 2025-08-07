pipeline {
    agent any

    environment {
        // Python version or virtual environment name
        VENV = 'venv'
    }

    stages {
        stage('Clone Repository') {
            steps {
                // Clone your GitHub repo (replace with your repo URL)
                git 'https://github.com/atharva1020/exp1/edit/v1/Jenkinsfile'
            }
        }

        stage('Setup Python Environment') {
            steps {
                script {
                    // Create a virtual environment
                    sh 'python3 -m venv ${VENV}'
                }
            }
        }

        stage('Install Dependencies') {
            steps {
                // Install required packages from requirements.txt
                sh '''
                    source ${VENV}/bin/activate
                    pip install --upgrade pip
                    pip install -r requirements.txt
                '''
            }
        }

        stage('Run Project / Tests') {
            steps {
                // Example: run tests with pytest
                sh '''
                    source ${VENV}/bin/activate
                    pytest
                '''
            }
        }
    }

    post {
        always {
            // Clean up virtual environment if needed
            sh 'rm -rf ${VENV}'
        }
        success {
            echo 'Build succeeded!'
        }
        failure {
            echo 'Build failed.'
        }
    }
}

pipeline {
    agent any

    environment {
        VENV = 'venv'
    }

    stages {
        stage('Clone') {
            steps {
               echo 'cloning repository from github...'
                )
            }
        }

        stage('Build') {
            steps {
                script {
                    // Setup virtual environment and install dependencies
                    sh 'python3 -m venv ${VENV}'
                    sh '''
                        source ${VENV}/bin/activate
                        pip install --upgrade pip
                        pip install -r requirements.txt
                    '''
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    // Example deploy commands - customize this!
                    echo 'Deploying application...'
                    // e.g. sh 'scp -r ./app user@server:/path/to/deploy'
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    // Run tests inside virtual environment
                    sh '''
                        source ${VENV}/bin/activate
                        pytest
                    '''
                }
            }
        }
    }

    post {
        always {
            // Clean up virtual environment after run
            sh 'rm -rf ${VENV}'
        }
        success {
            echo 'Pipeline succeeded!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}

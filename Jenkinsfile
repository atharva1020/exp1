pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git credentialsId: 'github-creds', url: 'https://github.com/your-username/your-repo.git'
            }
        }

        stage('Build') {
            steps {
                echo "Building the application..."
                // Add your build steps here
            }
        }

        stage('Test') {
            steps {
                echo "Running tests..."
                // Add test commands
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploying application..."
                // Add deployment commands
            }
        }
    }
}

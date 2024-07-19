pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                script {
                    echo "Cloning the repository..."
                }
                git branch: "${env.master}", url: 'https://github.com/aviman-8536/multibranch-pipeline-repo.git'
            }
        }
        stage('Install Dependencies') {
            steps {
                script {
                    echo "Installing dependencies..."
                    // Add commands to install dependencies, e.g., pip install -r requirements.txt
                }
            }
        }
        stage('Run Tests') {
            steps {
                script {
                    echo "Running tests..."
                    // Add commands to run your tests, e.g., pytest
                }
            }
        }
    }
    post {
        always {
            script {
                echo "Pipeline finished."
            }
        }
    }
}

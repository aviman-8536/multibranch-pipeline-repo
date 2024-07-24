pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                script {
                    echo "Cloning the repository..."
                }
                git url: 'https://github.com/aviman-8536/auto-trigger-repo.git', branch: 'release'
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
        stage('Read and Print Python Script') {
            steps {
                script {
                    echo "Reading and printing Python script..."
                    def scriptContent = readFile 'main.py'
                    echo scriptContent
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
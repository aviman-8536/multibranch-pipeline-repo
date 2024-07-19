pipeline {
    agent any

    stages {
        stage('Clone repository') {
            steps {
                git 'https://github.com/aviman-8536/multibranch-pipeline-repo.git'
            }
        }
        stage('Setup Python') {
            steps {
                sh 'ls -la' // List directory contents for debugging
                sh 'python3 --version'
            }
        }
        stage('Run main.py') {
            steps {
                sh 'python3 main.py'
            }
        }
        stage('Run Tests') {
            steps {
                sh 'mkdir -p test-reports' // Ensure test-reports directory exists
                sh 'python3 -m unittest discover -s tests -p "*.py" > test-reports/results.xml' // Run tests and save results
            }
        }
    }

    post {
        always {
            archiveArtifacts artifacts: '**/output/*', allowEmptyArchive: true
            junit 'test-reports/**/*.xml'
        }
        success {
            echo 'Pipeline succeeded!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}

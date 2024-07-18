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
                sh 'python3 --version'
                sh 'pip3 install -r requirements.txt'
            }
        }
        stage('Run main.py') {
            steps {
                sh 'python3 main.py'
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
